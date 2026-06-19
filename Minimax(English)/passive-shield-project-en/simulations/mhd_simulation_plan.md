# MHD SIMULATION PLAN

## Purpose

Numerically model the plasma interaction of the 3-layer Tesla-valve-topology passive magnetic shield under realistic Mars/Lunar conditions. Simulation outputs:
1. Plasma leakage rate (per condition)
2. Magnetopause / bow shock geometry
3. Reconnection leakage
4. Amplification effect of asymmetric topology
5. Optimization of design parameters

---

## 1. TOOL SELECTION

### Primary: BATS-R-US (NASA / University of Michigan)

**Why:**
- Standard in space physics (used in MESSENGER, MAVEN, MMS missions)
- Multi-scale MHD, parallel computing
- Mars, Mercury, Titan models open source
- Part of SWMF (Space Weather Modeling Framework)

**Setup:**
```bash
git clone https://github.com/MSTEM-UTSA/SWMF.git
cd SWMF
make
```

**Resources:**
- GitHub: https://github.com/MSTEM-UTSA
- Docs: https://csem.engin.umich.edu/research/swmf

### Secondary: OpenMHD (for education and fast iteration)

**Why:**
- Open source, small code base
- Fast prototyping
- Educational examples

**Setup:**
```bash
git clone https://github.com/PrincetonUniversity/OpenMHD.git
```

### Tertiary: Athena++ (for high performance when needed)

- Modern, GR+MHD
- MPI + OpenMP + GPU
- For performance

---

## 2. SIMULATION DOMAIN AND BOUNDARY CONDITIONS

### 2.1 Coordinate System

**Heliocentric Inertial (HCI):** Sun-centered, positioned at Mars orbit.

**Mars-centric:** Mars-centered, sun direction +X, north +Z (solar equator plane).

### 2.2 Grid Structure

**Region 1 (near field, 0-10 R_habitat):**
- High resolution: 1000×1000×1000
- R_habitat = 2500 m, so 0-25 km
- Adaptive: denser in reconnection zones

**Region 2 (far field, 10-100 R_habitat):**
- Low resolution: 200×200×200
- 25-250 km
- Sufficient for outer boundary conditions

### 2.3 Boundary Conditions

**Inflow boundary (+X face, sun direction):**
- $n_p$ = given condition
- $v_{sw}$ = given condition
- $B_{IMF}$ = given direction and magnitude
- $T_p$ = 1e5 K (typical)

**Other faces:**
- Free outflow (zero gradient)

---

## 3. INPUT PARAMETER SET

### 3.1 Fixed System Parameters

```python
SYSTEM = {
    "R_habitat": 2500,           # m, outer perimeter radius
    "R_mid": 1000,               # m, middle layer
    "R_inner": 100,              # m, inner core
    "B_edge_target": 20e-3,      # T, outer edge field
    "B_mid_segment": 0.3e-3,     # T, per middle layer ring contribution
    "B_inner": 0.5,              # T, inner core
    "N_mid_segments": 12,        # middle ring count
    "N_outer_turns": 5,          # outer turn count
    "asymmetry_angle_deg": 60,   # asymmetry angle between rings
}
```

### 3.2 Variable Conditions (Test Matrix)

| Test | Name | n_p (m⁻³) | v_sw (m/s) | B_IMF (T) | IMF direction |
|------|------|-----------|-----------|-----------|---------------|
| T1 | Typical (baseline) | 3e6 | 4e5 | 2e-9 | North (0°) |
| T2 | Average | 8e6 | 5e5 | 5e-9 | North |
| T3 | High pressure (SIR) | 2e7 | 6e5 | 1e-8 | Variable |
| T4 | ICME (extreme) | 3e7 | 7e5 | 2e-8 | North |
| T5 | Southward IMF (reconnection) | 8e6 | 5e5 | 5e-9 | South (180°) |
| T6 | Carrington-class | 1e8 | 1e6 | 1e-7 | Variable |
| T7 | Radial IMF | 5e6 | 5e5 | 5e-9 | Radial (90°) |
| T8 | Discontinuity transition | 1e7 | 6e5 | 1e-8 | 0° → 180° (process) |

### 3.3 Parameter Sweep (Topology Optimization)

```python
TOPOLOGY_SCAN = {
    "asymmetry_angle": [30, 45, 60, 90, 120],
    "N_mid_segments": [6, 12, 18, 24, 36],
    "B_edge": [10e-3, 15e-3, 20e-3, 30e-3, 50e-3],
    "B_inner": [0.1, 0.3, 0.5, 1.0, 2.0],
}
```

Total: 5 × 5 × 5 × 5 = 625 simulations. Each ~1 hour. Total: ~26 days, parallel ~3-4 days.

---

## 4. OUTPUT METRICS

Per simulation:

### 4.1 Scalar Metrics

```python
OUTPUTS = {
    "plasma_leakage_pct": None,         # percentage of plasma reaching inner zone
    "B_inside_avg_T": None,             # average B in inner zone
    "B_inside_max_T": None,             # maximum B in inner zone
    "magnetopause_radius_m": None,      # magnetopause radius
    "bow_shock_stand_off_m": None,      # bow shock distance
    "reconnection_rate": None,          # reconnection rate
    "magnetic_flux_Wb": None,           # total magnetic flux
    "energy_deposited_inside_J": None,  # energy entering inner zone
}
```

### 4.2 Vector/Field Outputs

- 2D slices (XY, XZ planes) of magnetic field map
- Plasma density map
- Flow vectors (streamlines)
- Current density (J)

### 4.3 Time Series (process tests)

For T8-like transition events, 1-second output for 0-60 minutes.

---

## 5. CRITICAL TEST SCENARIOS

### 5.1 Scenario A: Baseline (Typical Conditions)

**Input:** T1
**Expected:**
- Magnetopause R ~3000 m (slightly above R_habitat)
- Bow shock ~3500 m
- Plasma leakage: < 5%
- Reconnection: minimal (northward IMF)
- Inner zone B: 0.5-0.7 T

**Success criterion:** All inner zone dose targets met.

### 5.2 Scenario B: Southward IMF (Hardest Reconnection)

**Input:** T5 (southward IMF, 8e6, 5e5, 5nT, 180°)
**Expected:**
- Magnetopause compressed ~2500 m
- Reconnection active
- Plasma leakage: 10-20%
- **This shows the value of asymmetric topology**

**Success criterion:** Leakage 2-3× less than symmetric dipole comparison.

### 5.3 Scenario C: Extreme (ICME)

**Input:** T4 (3e7, 7e5, 20 nT, north)
**Expected:**
- Magnetic field compressed
- Shield still works, leakage 10-30%

**Success criterion:** Acute SPE dose < 5 mSv/hour.

### 5.4 Scenario D: Carrington Class (Historical Worst)

**Input:** T6 (1e8, 1e6, 100 nT)
**Expected:**
- Shield overloaded
- Partial leakage 50%+
- Structural risk (Lorentz forces)

**Success criterion:** System physically survives (does not collapse), leakage tolerable.

### 5.5 Scenario E: IMF Transition (Time Series)

**Input:** T8 (northward → southward transition, 30 minutes)
**Expected:**
- Magnetopause slowly compresses
- Reconnection activates
- Passive response (Lenz) limited contribution
- Slow recovery after transition

**Success criterion:** Dose increase < 50 mSv/hour during transition.

---

## 6. SIMULATION WORKFLOW

### 6.1 Phase 1: Setup and Baseline (Months 1-3)

1. BATS-R-US setup
2. Mars model configuration
3. Add system as "obstacle"
4. First baseline simulation (T1)
5. Result visualization (Paraview/VisIt)

### 6.2 Phase 2: Baseline Validation (Months 3-6)

1. Run all T1-T8 tests
2. Compare with symmetric dipole
3. Quantify asymmetric topology advantage

### 6.3 Phase 3: Parameter Optimization (Months 6-9)

1. Topology sweep (625 simulations)
2. Pareto front: B_edge vs mass vs leakage
3. Optimum point selection

### 6.4 Phase 4: Precise Validation (Months 9-12)

1. Re-test optimized design on T1-T8
2. Edge cases (corner cases)
3. Long-term stability (>1000 simulated seconds)

---

## 7. DATA MANAGEMENT

### 7.1 Output Format

**Vtk / HDF5:** Vector fields, 3D structures
**CSV:** Scalar metrics, time series
**JSON:** Configuration, metadata
**Markdown:** Automatic report generation

### 7.2 Storage

```bash
passive-shield-project/
├── simulations/
│   ├── raw/                # raw vtk/HDF5
│   │   ├── T1_baseline/
│   │   ├── T5_southward/
│   │   └── ...
│   ├── processed/          # CSV metrics
│   ├── figures/            # PNG/SVG charts
│   └── reports/            # Markdown auto-reports
```

### 7.3 Version Control

- Each simulation `git commit`'d (code, config, output)
- Parameter changes trackable
- Results reproducible

---

## 8. OPEN QUESTIONS / LIMITATIONS

### 8.1 MHD Limitations

MHD cannot resolve kinetic scales (ion gyroradius ~100 km in our system). Reconnection physics needs kinetic, Hall MHD, or full-PIC. Solution:

- MHD results for first estimate
- Critical reconnection zones for **PIC (Particle-in-Cell)** sub-simulations
- Hybrid approach: global MHD + local PIC

### 8.2 Plasma Kinetic Effects

- Ion gyroradius ~100 km (at 1 AU) → significant in 5 km system
- Electron gyroradius very small, negligible
- Result: leakage predictions may be 20-30% higher than MHD (pessimistic side)

### 8.3 Material Effects

In superconducting wire:
- AC losses (high-frequency IMF variations)
- Quench dynamics (loss of superconductivity)
- Structural resonance

These should be added to the simulation (later phase).

---

## 9. TIMELINE AND RESOURCES

**Total duration:** 9-12 months (Phases 1-4)
**Required:**
- 1 postdoctoral researcher (full-time)
- 1 master's student
- Computing: 100-200 CPU-cores, 6 months
- GPU optional (Athena++ speedup 5-10×)

**Cost:** $300-500K (researcher + computing + equipment)

---

## 10. EXPECTED OUTPUTS

1. **Academic publication (1-2 papers):**
   - "Tesla Valve Topology for Passive Magnetospheric Shielding"
   - "MHD Validation of Asymmetric Superconducting Loops for Habitat Protection"

2. **Design document (v1.0):**
   - Optimized topology
   - Engineering specifications
   - Performance guarantees

3. **Patent application (optional):**
   - Asymmetric ring topology
   - 3-layer passive shield architecture

4. **Open source contribution:**
   - Simulation code on GitHub
   - Parameter sets
   - Topology design tool (GUI)

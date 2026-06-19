# PHASE 1: LABORATORY VALIDATION

**Duration:** Years 1-3
**Budget:** $200-500K
**Output:** Optimized topology + 1-2 academic papers

---

## PURPOSE

Validate the 3-layer Tesla-valve-topology passive shield concept through MHD simulation and terrella experiment.

**Critical questions:**
1. Does asymmetric topology actually reduce leakage better than a symmetric dipole?
2. What are the optimum ring count, asymmetry angle, and current ratios?
3. How much can reconnection be suppressed by asymmetry?

---

## STAGE 1.1: MHD SIMULATION (3-6 months)

**Tool:** BATS-R-US (NASA)
**Details:** See `simulations/mhd_simulation_plan.md`

**Key outputs:**
- Baseline (T1) simulation → comparison with symmetric dipole
- Southward IMF (T5) → asymmetry benefit
- Parameter sweep (625 simulations)

**Staff:** 1 PhD student + 1 postdoc

---

## STAGE 1.2: TERRELLA EXPERIMENT (6-18 months)

### Experimental Setup

**Vacuum chamber:**
- Diameter: 2 m
- Length: 3 m
- Pressure: 10⁻⁶ Torr (turbo + cryo pump)
- Material: stainless steel 304

**Plasma source:**
- Type: Hollow cathode
- Current: 1-10 A
- Voltage: 50-200 V
- Plasma density: 10¹⁵-10¹⁷ m⁻³
- Energy: 5-50 eV
- Diameter: ~10 cm (focused beam)

**Test models (3D printed):**
- Symmetric dipole (baseline)
- Asymmetric 6 rings, 30° asymmetry
- Asymmetric 12 rings, 60° asymmetry
- Asymmetric 24 rings, 90° asymmetry
- Scale: 1:200 (R_outer = 12.5 cm)
- Wire: copper (not superconductor, only topology test)

**Magnetic field source:**
- Helmholtz coils: B=0-50 mT (homogeneous region)
- For plasma velocity: $v = E \times B$ drift

**Diagnostics:**
- Langmuir probe (density, temperature)
- Hall probe magnetometer (B field)
- High-speed camera (plasma behavior, 1000+ fps)
- Energy analyzer (particle spectrum)
- Optical emission spectroscopy (OES)

### Experimental Protocol

**Step 1: Characterization (1 week)**
- Calibrate plasma source
- Magnetic field map in empty vacuum
- Langmuir probe calibration

**Step 2: Symmetric baseline (2 weeks)**
- Symmetric dipole model
- Different B fields (0-30 mT)
- Plasma leakage measurement

**Step 3: Asymmetric topology sweep (8 weeks)**
- 5+ topologies, 5+ B fields = 25+ configurations
- 3+ repetitions per configuration
- Total: ~100 experiments

**Step 4: Reconnection tests (4 weeks)**
- Artificial IMF direction change
- Southward vs northward simulation (via rotational symmetry)

**Step 5: Data analysis and publication (8 weeks)**
- Statistical analysis
- Quantify asymmetric topology advantage
- Academic paper writing

### Expected Results

**If asymmetry hypothesis is correct:**
- Asymmetric 12 rings give 2-3× less leakage than symmetric dipole
- Under southward IMF conditions, asymmetric advantage is 3-5×

**If asymmetry hypothesis is wrong:**
- Ring count is irrelevant, only B magnitude matters
- 3-layer architecture unnecessary, single solenoid is enough

**Either outcome is valuable.** A wrong result ends the 10-15 year program early.

### Budget (Phase 1.2)

- Vacuum chamber setup: $50K
- Plasma source: $30K
- Helmholtz coils: $20K
- Diagnostics: $50K
- 3D printing material: $5K
- Postdoc salary (18 months): $90K
- PhD student (36 months partial): $60K
- Consumables + travel: $50K
- **Total: ~$355K**

---

## STAGE 1.3: TRANSITION CRITERIA → PHASE 2

**To proceed to Phase 2:**

✅ MHD simulation gives consistent results
✅ Terrella experiment results confirm simulation
✅ Asymmetric topology advantage quantified (at least 1.5×)
✅ Sufficient novelty for patent application
✅ Topology design finalized

**If criteria not met:**
- Negative terrella results → concept change
- MHD-terrella mismatch → model correction
- Budget overrun → re-scoping

---

## MILESTONES

| Month | Milestone |
|-------|-----------|
| 3 | BATS-R-US setup, first baseline simulation |
| 6 | Parameter sweep start, terrella setup |
| 12 | First terrella results, simulation comparison |
| 18 | Topology optimization complete |
| 24 | First academic paper (conference) |
| 30 | Second paper (peer-reviewed) |
| 36 | Patent application, Phase 2 planning |

---

## PUBLICATION STRATEGY

**Target journals:**
- Journal of Geophysical Research: Space Physics
- Acta Astronautica
- AIAA Journal of Spacecraft and Rockets
- Physics of Plasmas

**Target conferences:**
- AIAA SPACE Forum
- COSPAR (Committee on Space Research)
- AGU Fall Meeting
- IEEE Aerospace Conference

**Open access:** All publications open access (anti-monoculture principle)

# PHASE 3: GROUND PROTOTYPE (5 m diameter, 1:500 scale)

**Duration:** Years 7-12
**Budget:** $30-100M
**Output:** TRL 6-7, full-scale manufacturability proof

---

## PURPOSE

Build a **full prototype** at 5 m diameter (1:500 scale, instead of 5 km). All components use the same technology and materials as the full-scale orbit prototype.

**Critical questions:**
1. Do full-scale production processes work?
2. Is the integration of all components smooth?
3. Does quench management work in real environment?
4. Is reliability there for 1+ year continuous operation?

---

## SYSTEM: 5 m DIAMETER FULL PROTOTYPE

**Note:** The real system is 5 km diameter, we build a 1:500 scale (5 m) prototype. MHD is scalable (Mach number, Alfvén number preserved), but **mechanical integration, production processes, quench management** are tested at full scale.

### Components

#### 1. YBCO Superconducting Wire (300+ km)
- Production partners: SuperPower, Fujikura, SuNam
- Properties: 12mm width, 0.1mm thickness, GdBa₂Cu₃O₇
- Substrate: Hastelloy (mechanical) + graphene (NASA MAARSS approach)
- Total: 300-500 km (sufficient to scale up production lines for Phase 3)

#### 2. Core Solenoid (R=0.5m, L=1m)
- For this prototype: can be 1:200 scale (production proof only)
- Target: B = 0.1 T (prototype, not 0.5 T)
- 1,000 turns, copper test winding initially

#### 3. Middle Layer (12 rings, R=5m)
- Full-scale topology (5 m instead of 1000m → 1:200 scale)
- Asymmetric placement, 60° cyclic
- Each ring 0.1-0.3 mT contribution
- Total: 75 m wire × 12 rings = 900 m

#### 4. Outer Perimeter (5 m diameter, 5 turns)
- Full-scale: 5 m diameter (1:500 scale)
- B_edge = 5-10 mT (lower in prototype)
- Total: 80 m wire

### Plasma Test Chamber

**Vacuum chamber:**
- Diameter: 8 m (5 m shield + 1.5 m measurement area)
- Length: 20 m (for plasma flow)
- Pressure: 10⁻⁷ Torr (ion pump + cryo)

**Plasma source:**
- Type: RF (radiative heating, 1-5 kW)
- Output: 5-50 eV, ~10¹⁶ m⁻³
- Flow speed: 5-50 km/s (via magnetic pump)
- Diameter: 50 cm

**Diagnostics:**
- Langmuir probe (5+ positions)
- Hall probe magnetometer (3-axis, 3D map)
- High-speed camera
- Emission spectroscopy
- Energy analyzer

### Control and Monitoring (No Active Control!)

**Monitoring only:**
- Current level (per ring)
- Temperature (per ring + cryocooler)
- Magnetic field (inner and outer)
- Plasma parameters
- Vacuum pressure

**Control:**
- Only emergency shutdown (quench detection)
- Dump resistor activation
- Safety interlocks

---

## STAGES

### 3.1: Facility Setup (Years 7-8)

**Location selection:**
- 8 m diameter, 20 m length vacuum chamber
- Existing facility (NASA, ESA, JAXA, university) can be leased
- Example: NASA Glenn Research Center (historic vacuum chambers), MIT Lincoln Lab

**Infrastructure:**
- Power: 1 MW
- Cooling: 100 kW (cryocoolers)
- Plasma source: 50 kW
- Data collection: 1000+ sensors

**Facility budget:** $20-40M (modification of existing facility)

### 3.2: Superconductor Production Line (Years 7-9, parallel)

**Target:** 300+ km YBCO strip production
- Current manufacturer capacity: annual ~1,000-5,000 km (very large)
- 300 km allocation for Phase 3 is sufficient
- Special substrate (graphene) addition: $2M R&D

**Supply:**
- SuperPower Inc. (USA)
- Fujikura (Japan)
- SuNam (South Korea)
- THEVA (Germany)

**Wire budget:** $5-10M

### 3.3: System Manufacturing (Years 9-10)

**Inner core:**
- 0.5 m diameter solenoid structure
- Carbon fiber support frame
- 1,000 turns, YBCO wire

**Middle and outer layer:**
- 12 rings (R=5 m), asymmetric placement
- 5 rings (R=5 m)
- Mechanical skeleton, carbon fiber

**Cooling:**
- 5× cryocooler (5 K)
- 1× backup
- Distribution manifolds

**Quench management:**
- Dump resistor bank (per ring)
- Fiber-optic temperature sensors
- Controlled energy dump

**Manufacturing budget:** $20-30M

### 3.4: Plasma Testing (Years 10-12)

**Test 1: Basic characterization (3 months)**
- Magnetic profile in plasma flow
- Magnetopause formation observation
- Bow shock detection

**Test 2: Asymmetric vs symmetric (3 months)**
- Two configurations at same B value
- Leakage difference measurement

**Test 3: Reconnection (6 months)**
- Artificial IMF direction change
- Performance under southward conditions

**Test 4: Long-term operation (12 months)**
- Continuous under plasma
- Flux loss measurement
- Quench management validation
- Recharge procedure test

**Test budget:** $10-20M (12 months, 1 shift/day operation, equipment + personnel)

---

## TOTAL PHASE 3 BUDGET

| Item | Amount |
|------|--------|
| Facility setup | $20-40M |
| YBCO wire production | $5-10M |
| System manufacturing | $20-30M |
| Plasma tests (1 year) | $10-20M |
| Personnel (5 years, ~10 people) | $15-20M |
| Management, licensing, insurance | $5-10M |
| Reserve | $5-10M |
| **TOTAL** | **$80-140M** |

**Risky items:**
- Facility setup (location-dependent)
- Graphene substrate delays in wire production
- Unexpected problems during testing

**Realistic budget:** $100M, compatible with NASA NIAC or ESA CDF programs.

---

## OUTPUTS

1. **5 m diameter full prototype** (functional)
2. **Plasma test data** (open access)
3. **TRL 6-7 certification** (NASA standard)
4. **Patent update** (topology + quench management)
5. **2-3 academic papers**
6. **Phase 4 planning document**

---

## TRANSITION CRITERIA → PHASE 4

✅ 12 months uninterrupted plasma test successful
✅ Quench management validated
✅ Recharge procedure works
✅ Flux loss < 1%/year
✅ Engineering specifications ready for full-scale (5 km) system
✅ Budget and timeline reasonable

**If criteria not met:** Redesign, additional 2-3 years.

---

## OPEN STANDARDS

- All wire properties published
- Plasma test procedures standardized
- Topology design open source
- Patent licensing: non-commercial free, commercial royalty
- All data in open archive

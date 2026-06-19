# PHASE 2: CUBESAT DEMONSTRATION

**Duration:** Years 3-7
**Budget:** $2-5M
**Output:** Concept validated in space, TRL 5-6

---

## PURPOSE

Test the topology validated in Phase 1 in an **actual space environment**. This goes beyond simulation and laboratory.

**Critical questions:**
1. Can the superconducting wire survive launch vibration?
2. Does the deployment mechanism work in space?
3. Is passive current induction (persistent mode) functional?
4. Does the shield actually form in plasma environment?

---

## CONCEPT: 3U CUBESAT + DEPLOYABLE SUPERCONDUCTING RING

### CubeSat (Bus)

**Form factor:** 3U (10×10×30 cm, ~4 kg)
**Built-in systems:**
- OBC (On-Board Computer): ARM Cortex-M4
- Telemetry: UHF/VHF (amateur band, 9.6 kbps)
- Command receiver: UHF
- Power: Li-ion + solar panel (3-5 W)
- Star tracker: fiber gyro
- Magnetometer: 3-axis fluxgate, ±65 µT
- GPS: LEO positioning

### Deployable Ring (Payload)

**Launch configuration:**
- Ring tightly wound, ~10 cm diameter spool
- YBCO strip spool: 50 m (5 cm × 5 cm × 10 cm volume)
- Protective cover (release mechanism)

**After deployment:**
- Ring diameter: ~16 m (radius 8 m)
- 1 turn, thin YBCO
- Self-expanding mechanism (shape memory alloy + spring)

**Current induction:**
- Once in orbit, **persistent current** is induced
- Method: External coil + switch (Flux pump technique)
- Target current: 100-500 A (limited, just concept validation)
- Induced once, stays in persistent mode

### Measurement Targets

**Primary:**
- Deployment success in space
- Current persistence (1-2 years)
- Ring geometry preservation

**Secondary:**
- Plasma interaction in orbit (at TLE altitude ~400 km)
- Structural vibration modes
- Thermal performance (sun/shadow cycle)

### Orbit Strategy

**Target orbit:** 400-600 km, ~28° inclination (SpaceX rideshare compatible)
**Lifetime:** 1-2 years via natural orbital decay
**Cost:** Rideshare at $300-500K (3U slot)

---

## STAGES

### 2.1: Design (6-12 months)

**Mechanical:**
- Deployment mechanism (TESS-R asteroid sampling concept)
- Shape memory alloy (Nitinol) trigger
- Ring structural analysis (modal analysis)

**Thermal:**
- YBCO 5K cooling (mini cryocooler, 50 g)
- Sun/shadow gradient management
- Passive radiation (deep space side)

**Electronics:**
- COTS components (preferably rad-hard)
- Deployment timing (orbit + position)
- Data packet: 10 kB/day (sufficient)

**Software:**
- OBC firmware (C)
- Ring control (deployment only, no active control)
- Telemetry packaging

### 2.2: Ground Tests (12-18 months)

**Mechanical tests:**
- Vibration: 14 g RMS (qualification)
- Shock: 100 g, 1 ms
- Thermal vacuum: -100°C to +100°C, 10⁻⁵ Torr
- Deployment: 0 g simulation, real atmosphere

**Superconductor tests:**
- 5K cryocooler performance
- YBCO strip vibration test
- Current induction demo (on ground, with large coil)

**Integration:**
- All subsystems
- EMI/EMC tests
- Functional tests (all modes)

### 2.3: Launch and Operation (24-36 months)

**Launch:**
- SpaceX Falcon 9 rideshare (e.g., Transporter-5)
- Orbit: 525 km, sun-synchronous
- Insertion: within 1-2 months

**LEOP (Launch and Early Orbit Phase):**
- Telemetry setup
- Health check
- Deployment timing (orbit + position optimization)

**Operation:**
- Post-deployment: 1 year data
- Total 2 years orbital lifetime
- Ground station: Amateur radio network + dedicated receivers

### 2.4: Data Analysis and Publication (36-48 months)

**Data:**
- Deployment success (y/n)
- Current time series
- Ring geometry
- Plasma interaction (limited, plasma is dense at 525 km)

**Publication:**
- AIAA/Acta Astronautica paper
- Topology design validation
- Phase 3 planning

---

## BUDGET

| Item | Amount |
|------|--------|
| CubeSat bus (COTS) | $200K |
| YBCO ring payload | $300K |
| Cryocooler (mini) | $150K |
| Mechanical design + manufacturing | $200K |
| Ground tests (vibration, thermal vacuum) | $300K |
| Software development | $100K |
| Launch (rideshare) | $500K |
| Operation (1-2 years) | $300K |
| Data analysis | $100K |
| Conference + publication | $50K |
| Management + reserve | $300K |
| **TOTAL** | **~$2.5M** |

---

## RISKS AND MITIGATION

| Risk | Probability | Impact | Mitigation |
|------|-------------|--------|------------|
| Deployment fails | Medium | Mission failure | Strict ground tests, redundant trigger |
| YBCO quench on vibration | Medium | Current loss | Mechanical support, vibration isolator |
| Cryocooler fails | Medium | Wire warms, current loss | Passive radiation cooling, redundancy |
| Plasma measurement weak (525 km too dense) | High | Low scientific value | At least concept is validated |

---

## TRANSITION CRITERIA → PHASE 3

✅ Ring successfully deployed in space
✅ Persistent current retained for 6+ months
✅ Ring geometry remained stable
✅ At least 1 SPE event passage recorded
✅ Patent updated
✅ Sufficient data for full-scale ground prototype

**If all criteria not met:** Redesign, additional 6-12 months.

---

## OPEN SCIENCE POLICY

- All data raw on NASA Open Data Portal
- All code open source
- Ring design patented but licensed open (royalty-free non-commercial)
- Academic groups invited (workshop + data access)

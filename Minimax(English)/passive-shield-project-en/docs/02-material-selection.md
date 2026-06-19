# MATERIAL SELECTION

## Superconducting Wire and Other Components for the Passive Asymmetric Magnetic Shield

**Version:** 0.1 — 2026-06-05

---

## 1. SUPERCONDUCTING WIRE

### 1.1 Requirements

- **Critical temperature (T_c):** > 77 K (operable at liquid nitrogen temperature)
- **Critical current density (J_e):** > 1×10¹¹ A/m² (at 5K), > 1×10¹⁰ A/m² (at 77K)
- **Mechanical strength:** resistant to hoop stress and vibration
- **Radiation resistance:** 25 years in 1 Gy/hour GCR environment
- **Dimensions:** 10-20 m length, weldable
- **Cost:** $10-50/kA-m (~$300M wire total for Phase 4)

### 1.2 Candidate Materials

#### A. YBCO (YBa₂Cu₃O₇-δ) — Primary Choice

**Advantages:**
- High T_c = 92 K (liquid nitrogen cooling possible)
- High J_e = 1-9×10¹¹ A/m² (5K), 6×10¹⁰ A/m² (77K)
- Mature industrial production (SuperPower, Fujikura, SuNam)
- Available as strip (4-12mm width)
- **Price: $20-50/kA-m (2026), expected $5-15/kA-m by 2030**

**Disadvantages:**
- Brittle ceramic, mechanical support required
- Medium radiation sensitivity
- High AC losses (but we use DC)

**Suppliers:**
- **SuperPower Inc.** (USA, Schenectady NY) — 4-12mm strip
- **Fujikura Ltd.** (Japan) — 10mm standard
- **SuNam Co.** (South Korea) — high J_e strips
- **THEVA GmbH** (Germany) — European supply
- **Shanghai Superconductor Technology** (China) — cheap, high volume

**Total global capacity:** ~5,000-10,000 km/year (2026). For Phase 4: 2,000 tons = ~12,000 km (a few years of production). Possible but **early supply contract is critical**.

#### B. Bi-2212 (Bi₂Sr₂CaCu₂O₈) — Secondary

**Advantages:**
- Round wire form (easier winding)
- Very high J_e possible
- Long research history

**Disadvantages:**
- T_c = 85 K (slightly lower)
- AC losses
- Heat treatment required
- Currently limited production

**Suitability:** For high-performance areas, not the main system.

#### C. MgB₂ (Magnesium Diboride) — Tertiary

**Advantages:**
- Cheap, abundant material
- T_c = 39 K (lower, but easier cooling)
- Commercially available as wire

**Disadvantages:**
- J_e very low: ~10⁹-10¹⁰ A/m² (10-100× lower)
- Much heavier system required vs YBCO

**Suitability:** Backup option if YBCO cannot be sourced.

#### D. Iron-Based Superconductor — Future

**Advantages:**
- High T_c (50-100 K range)
- Cheaper raw materials
- More magnetically field-tolerant
- Industrial production expected 2025-2030

**Disadvantages:**
- Not yet mature
- Commercial strip not available in 2026

**Suitability:** Alternative for Phase 4 (year 12-25). Early research.

### 1.3 Recommended Wire Architecture

**Primary choice:** YBCO 12mm strip, 0.1mm thickness, Hastelloy substrate
- **Manufacturer:** SuperPower (USA) or Fujikura (Japan)
- **Specification:**
  - Width: 12 mm
  - Thickness: 0.1 mm (superconductor layer)
  - Substrate: 50 μm Hastelloy C-276
  - Coating: 20 μm copper (thermal stability)
  - Total thickness: 170 μm
  - J_e (5K, self-field): 9×10¹¹ A/m²
  - I_max (single strip): 1.08 MA

**Parallel strip bundle:** 5-15 parallel strips (safety + capacity)
- 5 parallel: 5.4 MA max, 4 strips as backup
- 15 parallel: 16.2 MA max, excessive backup

**Welding:** Joining strips is challenging. Methods:
- **Ultrasonic welding** (~1 m length joint, low resistance)
- **Laser welding** (shorter, higher resistance)
- **Mechanical compression** (easiest, demountable)

**Target joint resistance:** < 10⁻¹² Ω (for persistent current retention)

---

## 2. SUBSTRATE MATERIAL

### 2.1 Why It Matters

YBCO alone is very brittle. A 5 km diameter ring must withstand 1.5 kN/m hoop stress. YBCO cannot do this. The substrate carries the mechanical load.

### 2.2 Candidates

#### A. Hastelloy C-276 (Ni-Cr-Mo Alloy) — Primary

**Advantages:**
- Non-magnetic (does not disturb shield)
- High corrosion resistance
- Compatible with superconductor production
- Mature material

**Disadvantages:**
- High density: 8.9 g/cm³
- Medium mechanical properties

**Use:** Standard substrate in YBCO production line

#### B. Stainless Steel 316L — Alternative

**Advantages:**
- Cheap, abundant
- Good mechanical properties

**Disadvantages:**
- Magnetic (paramagnetic, small effect)
- Corrosion risk (no humidity in space, not a problem)

**Use:** Secondary option

#### C. Graphene-Reinforced Composite — Future (NASA MAARSS)

**Advantages:**
- Very high strength-to-weight ratio
- Non-magnetic
- Low density: 1.5-2 g/cm³
- **NASA MAARSS study found graphene-substrate YBCO 5× more efficient**

**Disadvantages:**
- New technology
- Production not yet mature
- Difficult integration with superconductor production line

**Use:** R&D in Phases 1-2, application in Phase 3

### 2.3 Recommended Structure

**Sandwich composite:**
- 0.1 mm YBCO
- 50 μm Hastelloy (production compatibility)
- 0.5-1 mm carbon fiber composite (structural support)
- 50 μm copper coating (thermal stability)

**Total thickness:** 0.7-1.2 mm
**Total cross-sectional area:** 12 mm × 1 mm = 12 mm² (10× standard strip)
**Current capacity:** 9×10¹¹ × 12×10⁻⁶ = 10.8 kA (single strip!)

**This means 1-2 parallel strips are enough for the 5-10 kA requirement. Significant mass savings.**

---

## 3. CRYOCOOLER

### 3.1 Requirements

- **Operating temperature:** 5 K (for high J_e YBCO)
- **Cooling capacity:** 1 W @ 5 K (per cryocooler)
- **Power consumption:** 1-2 kW for 1 W @ 5 K cooling
- **Lifetime:** > 25 years (or modular replacement)
- **Mass:** < 200 kg
- **Vibration:** low (must not disturb superconductor)

### 3.2 Candidates

#### A. GM (Gifford-McMahon) Cooler — Primary

**Advantages:**
- Commercially available (Sunpower, Cryomech)
- 5-10 W @ 4.2 K (small models)
- Space-adapted versions exist
- 10+ year lifetime (proven in space missions)

**Disadvantages:**
- Heavy (150-300 kg)
- High power (1.5-2.5 kW @ 5 K)
- Vibration (mechanical compressor)

**Example:** Sunpower CryoTel GT (150 kg, 1.5 kW → 1 W @ 4.2 K)

#### B. Pulse Tube Cooler — Secondary

**Advantages:**
- Vibration-free (pulse tube principle)
- Longer life (no moving parts)
- Space-optimized

**Disadvantages:**
- Heavier
- More expensive
- Limited supply

**Example:** Lockheed Martin / NASA Goddard designs

#### C. Passive Radiation Cooling — Auxiliary

**Advantage:** Zero power down to 50-100 K
**Disadvantage:** Cannot reach 5 K (only pre-cooling)
**Use:** Before GM/pulse tube, 50% power savings

### 3.3 Recommended Configuration

**5 active + 1 backup GM cryocooler:**
- Each: 150 kg, 1.5 kW
- 5 active: 750 kg, 7.5 kW
- 1 backup: 150 kg, 1.5 kW (standby)
- **Total: 900 kg, 9 kW**

**Lifetime management:** Replacement every 7-10 years
- First replacement: Year 7-10 (from local sources)
- Total: 2-3 replacements over 25 years

---

## 4. STRUCTURAL MATERIALS

### 4.1 Ring Skeleton

**Requirements:**
- Maintain 5 km diameter circular geometry
- Withstand Lorentz forces
- Manage thermal expansion (-150°C to +150°C, shadow/sun)
- Must be non-magnetic (does not disturb shield)

**Choice:** Carbon fiber composite (CFRP)
- Density: 1.5-1.8 g/cm³
- Tensile strength: 3-7 GPa
- Non-magnetic
- Thermal expansion: ~0 (longitudinal)

**Architecture:**
- 12-24 main beams (carbon fiber, 5-10 cm diameter)
- Cross connections (thinner)
- Clamps carrying ring segments

### 4.2 Core Solenoid Frame

**Higher density forces:** 100,000 N/m hoop stress at 0.5 T
**Choice:** Carbon fiber or high-strength aluminum
- Al-7075-T6: tensile 570 MPa, density 2.8 g/cm³
- Carbon fiber: tensile 3-7 GPa, density 1.6 g/cm³

**Carbon fiber preferred** but more expensive.

### 4.3 Mounting Brackets

**Choice:** Aluminum 7075 or titanium
- Aluminum: light, non-magnetic
- Titanium: stronger but expensive

---

## 5. INSULATION MATERIALS

### 5.1 Multi-Layer Insulation (MLI)

**Requirements:**
- Minimum heat transfer from 5 K surface to 300 K environment
- Must work in vacuum (no convection)
- 25-year lifetime

**Choice:** 20-30 layer MLI
- Each layer: 12 μm Mylar (aluminum-coated)
- Spacer layer: Dacron mesh
- Total: 2-3 cm thickness
- **Heat transfer per surface: 1-5 W/m²** (at 5 K)

**Suppliers:** Sheldahl, Dunmore, TÜBİTAK (Istanbul)

### 5.2 Radiation Insulation

**Requirements:**
- Absorb GCR and SPE protons
- 25-year cumulative dose

**Choice:**
- 2-5 cm polyethylene (high hydrogen content)
- 1-2 mm aluminum (X-ray reduction)
- Total: ~5 g/cm² (partial GCR reduction)

---

## 6. MONITORING AND CONTROL SYSTEMS

### 6.1 Sensors

**Magnetic field:**
- 3-axis fluxgate magnetometer (inner region, 5+ units)
- Hall probe (outer region, 10+ units)

**Current:**
- Rogowski coils (per ring)
- Hall-effect current sensor (backup)

**Temperature:**
- Thermocouples (per segment, 100+ units)
- Fiber Bragg grating (quench detection, 1 ms response)

**Structural:**
- Strain gauge (on ring, 50+ units)
- Accelerometer (vibration monitoring)
- Acoustic emission (crack detection)

**Plasma:**
- Langmuir probe (optional, around base)
- Energy analyzer (radiation environment)

### 6.2 Data Collection

**OBC:** Space-grade rad-hard computer
- Example: NASA Goddard RAD750 (older) or RAD5500 (newer)
- Data rate: 1 MB/hour, compressed
- Storage: 1 TB SSD (radiation-hardened)

**Telemetry:** Continuous data to ground station
- X-band downlink (high speed)
- S-band uplink (command)
- Data rate: 100 kbps (downlink)

### 6.3 Active Control (Minimum!)

**Philosophy:** Minimum possible active control. Only:
- **Emergency shutdown** (quench detection → dump resistor)
- **Cryocooler control** (temperature adjustment)
- **Current balancing** (very small corrections, 1-10 A)

**Total active control power:** < 100 W
**Smart decision:** Topology is faithful to the zero-electronics principle

---

## 7. COST SUMMARY

| Material | Unit Price | Total (Phase 4) |
|----------|------------|-----------------|
| YBCO wire (2000 tons) | $100-200/kg | $200-400M |
| Substrate + coating | $50-100/kg | $100-200M |
| Cryocooler (6 units) | $1-2M/unit | $6-12M |
| Carbon fiber structure | $50-100/kg | $50-100M |
| MLI insulation | $500/m² | $10-20M |
| Sensors + data collection | $5M | $5M |
| Active control | $1M | $1M |
| **Total materials** | | **$400-800M** |

**Largest cost item is wire + substrate.** This makes early supply chain research in Phases 1-2 critical.

---

## 8. CONCLUSIONS AND RECOMMENDATIONS

**Primary material choice:**
- YBCO 12mm strip, Hastelloy substrate
- Carbon fiber structural support
- 5+1 GM cryocooler configuration
- Passive MLI + active GM cooling

**Early action required (Phases 1-2):**
- Long-term supply discussions with 5+ manufacturers
- Additional R&D funding for special substrate (graphene)
- Cryocooler lifetime tests
- Long-term current endurance tests

**Secondary options (backup):**
- Bi-2212 (high performance)
- MgB₂ (low performance, cheap)
- Iron-based (future, 5-10 years)

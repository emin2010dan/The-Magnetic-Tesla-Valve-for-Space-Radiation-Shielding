# DIAGRAMS

This directory contains diagrams that visualize the project. Currently **text descriptions** are available; **visual files** (PNG/SVG) will be produced in a later phase.

---

## D1: System Architecture (3 Layers)

**File:** `system-architecture.png` (to be produced)

**Description:**

```
                    ┌─────────────────────┐
                    │  LAYER 3: OUTER     │
                    │  R = 2500 m         │
                    │  5 thin rings       │
                    │  B_edge = 20 mT     │
                    │  Passive, light     │
                    │  ~3 tons, 80 km wire│
                    ├─────────────────────┤
                    │  LAYER 2: MIDDLE    │
                    │  R = 1000 m         │
                    │  12 asymmetric rings│
                    │  60° cyclic         │
                    │  ΔB ≈ 0.3 mT/ring   │
                    │  ~3 tons, 75 km wire│
                    ├─────────────────────┤
                    │  LAYER 1: INNER     │
                    │  R = 100 m          │
                    │  L = 200 m          │
                    │  20,000 turns       │
                    │  B = 0.5 T          │
                    │  ~490 tons, 12.5 km │
                    └─────────────────────┘
                          BASE STRUCTURES
                       (100-1,000 people)
```

---

## D2: Magnetic Field Profile

**File:** `magnetic-profile.png` (to be produced)

**Description:** Semi-logarithmic graph, r vs |B(r)|

- Inner solenoid: 0.5 T (center) → ~0.3 T (R=100m)
- Middle layer: 5-10 mT (around R=1000m)
- Outer perimeter: 20 mT (R=2500m)
- Beyond: rapid decrease, ~5 mT (R=3000m)

---

## D3: Plasma Flow (MHD Expected)

**File:** `plasma-flow.png` (to be produced)

**Description:** Plasma flow lines in XY plane

- Wind comes from left (sun direction)
- Hits ring at Layer 3 (R=2500m)
- Bow shock forms (R=2700m)
- Plasma is deflected, flows around
- Magnetopause (R=2400m) protects inner zone
- Magnetotail (right side, R>5000m) extends backward

---

## D4: R&D Roadmap (Timeline)

**File:** `phase-timeline.png` (to be produced)

**Description:** Horizontal time axis, 4 phases shown

```
Year:  0    3    5    7   10   15   20   25
       │    │    │    │    │    │    │    │
Phase1 ████████  MHD simulation + terrella
Phase2         ██████████████  CubeSat
Phase3                       ████████████████  Ground prototype
Phase4                                       ████████████  Space deployment
```

---

## D5: Tesla Valve Topology Detail

**File:** `tesla-topology.png` (to be produced)

**Description:** Asymmetric placement of 12 rings

```
       ┌─────────────────────┐
       │  Ring 1 (R=1000m)   │  plane: 0°
       └─────────────────────┘
       ┌─────────────────────┐
       │  Ring 2 (R=1000m)   │  plane: 30°
       └─────────────────────┘
       ... (60° cyclic, up to 12 rings)
       ┌─────────────────────┐
       │  Ring 12 (R=1000m)  │  plane: 330°
       └─────────────────────┘
```

**Critical observation:** Ring planes are cyclic, asymmetric placement. This creates a "hard to pass" geometry for plasma.

---

## D6: Energy Flow

**File:** `energy-flow.png` (to be produced)

**Description:** Sankey diagram

- Sun: 1.36 kW/m² (at 1 AU)
- At Mars: 590 W/m² (1.5 AU)
- Hits 5 km diameter area: 4.6 GW (solar energy)
- 99.5% deflected by shield
- Leakage to inner zone: ~20 MW (heat, then expelled)
- Reaches base structures: 0.5-1 mSv/day (radiation, below target)

---

## D7: Quench Management Flow Chart

**File:** `quench-management.png` (to be produced)

**Description:** Quench detection → response flow

```
Temperature sensor (1 ms sampling)
     │
     ▼
ΔT > 0.5 K?
     │
     ├─ No → Normal operation
     │
     └─ Yes → Quench alarm
              │
              ▼
         Dump resistor activation (10 ms)
              │
              ▼
         Energy converts to heat
              │
              ▼
         Neighboring segments isolated
              │
              ▼
         Alarm to ground station
              │
              ▼
         Repair mission within 7 days
```

---

## HOW TO PRODUCE

These diagrams can be produced in a later phase with Python (matplotlib/plotly) or SVG. An interactive HTML page can also be made using the visual-page skill.

**Recommended first diagram:** D1 (System Architecture) — summarizes the project at a glance.

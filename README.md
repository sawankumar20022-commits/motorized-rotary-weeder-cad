# Motorized Rotary Weeder Mechanism (CAD Design & Fabrication)

![License](https://img.shields.io/badge/License-MIT-blue.svg)
![CAD](https://img.shields.io/badge/CAD-CATIA%20V5-orange.svg)
![Domain](https://img.shields.io/badge/Domain-Farm%20Machinery%20%26%20Power-green.svg)
![Tooling](https://img.shields.io/badge/Tooling-Locating%20%26%20Drilling%20Jig-red.svg)

A complete mechanical design, 3D CAD model, manufacturing documentation, and design calculation package for a **Motorized Rotary Weeder Mechanism** designed for efficient inter-row weeding and soil aeration in vegetable and grain crops.

Designed using **CATIA V5**, this project includes parametric 3D parts, assembly configurations, 2D workshop manufacturing drawings with GD&T, a custom motor mount **locating & drilling jig**, and mechanical design calculation scripts in **Python**.

---

## Table of Contents
- [Project Overview](#project-overview)
- [Key Mechanical Specifications](#key-mechanical-specifications)
- [System Architecture & Subsystems](#system-architecture--subsystems)
- [Design Calculations (Python)](#design-calculations-python)
- [Locating & Drilling Jig Design](#locating--drilling-jig-design)
- [Bill of Materials (BOM)](#bill-of-materials-bom)
- [Manufacturing & Assembly Workflow](#manufacturing--assembly-workflow)
- [Repository Structure](#repository-structure)
- [How to Run the Calculations](#how-to-run-the-calculations)
- [Author & Academic Context](#author--academic-context)

---

## Project Overview

Weed infestation in row crops reduces crop yields by up to 35% due to nutrient competition. Manual weeding using hand hoes is slow, physically exhausting, and labor-intensive. This **Motorized Rotary Weeder** delivers an ergonomic, high-throughput mechanical solution:
1. **Soil Cutting & Weed Up-rooting:** High-carbon curved L-shaped blades rotate at high angular velocity, shearing weed roots 20–40 mm below the soil surface.
2. **Power Transmission:** A compact petrol engine/motor drives a dual-stage V-belt pulley reduction system to achieve optimal cutting torque.
3. **Ergonomic Walk-Behind Operation:** Lightweight chassis with adjustable depth skid and anti-vibration rubber mounted handlebars.
4. **Safety & Protective Shielding:** Heavy-gauge sheet metal mudguard shields the operator from soil throw and prevents root entanglement.

---

## Key Mechanical Specifications

| Parameter | Specification | Notes |
| :--- | :--- | :--- |
| **Weeding Width** | 260 mm (Adjustable for 200–300 mm crop rows) | Ideal for maize, cotton, and vegetables |
| **Weeding Depth** | 20 mm – 45 mm | Controlled via rear depth skid |
| **Power Source** | 1.5 kW (2.0 HP) 4-Stroke Engine / Electric Motor | Operating at 2400 RPM |
| **Rotor Operating Speed** | 250 – 280 RPM | Optimal soil cutting & root slicing |
| **Transmission Type** | B-Section V-Belt & Pulley Reduction (Approx. 8.5:1 ratio) | Smooth slip protection against rocks |
| **Blade Geometry** | Curved L-Type Blades (6 blades arranged at 60° offset) | High-Carbon Spring Steel (En45) |
| **Rotor Diameter** | 220 mm outer cutting sweep diameter | Hardened cutting edge |
| **Chassis Material** | Mild Steel Angle Iron (35x35x3 mm) & Tube (Ø25.4 mm) | High torsion and vibration resistance |

---

## System Architecture & Subsystems

```
[ Power Unit: 1.5 kW Motor @ 2400 RPM ] 
                 │
      (V-Belt & Pulley Reduction: Ø60mm to Ø250mm)
                 ▼
[ Intermediate Reduction / Counter-Shaft ]
                 │
      (Secondary Reduction Drive)
                 ▼
[ Rotor Drive Shaft (Ø25mm) ] ──▶ [ Pillow Block Bearings (UCP 205) ]
                 │
                 ▼
[ Rotary Hub with 6x Curved High-Carbon Steel Blades (En45) ]
                 │
                 ▼
[ Soil Root Slicing (250 RPM) ] ──▶ [ Protective Sheet Metal Mudguard ]
```

1. **Rotor Cutting Assembly:** Central hex/cylindrical shaft with 6 curved blades arranged symmetrically at 60° intervals to maintain dynamic balance and eliminate cutting pulsations.
2. **Power Transmission:** Dual V-belt system provides natural overload clutching—if a blade hits an underground obstacle/rock, the belt slips safely without stalling the engine or shearing shafts.
3. **Chassis & Depth Skid:** Rugged welded structural frame with an adjustable rear skid shoe that regulates working depth and absorbs reaction forces.

---

## Design Calculations (Python)

A dedicated Python script (`scripts/weeder_design_calculations.py`) is provided to calculate:
- **Peripheral Blade Tip Speed (\(v_t\)):**
  $$v_t = \frac{\pi \times D_{rotor} \times N_{rotor}}{60} \quad (\approx 2.88\text{ m/s})$$
- **Soil Cutting Torque (\(T_{soil}\)) & Power Requirement:**
  $$P_{req} = \frac{2 \pi N T}{60 \times \eta_{trans}}$$
- **Torsional Shaft Diameter Check:** Ensures minimum factor of safety \(FOS > 2.5\) under peak soil resistance.

---

## Locating & Drilling Jig Design

A custom **Workbench Locating & Drilling Jig** was engineered in CATIA V5 to solve motor mounting alignment:
* **The Problem:** Misaligned motor mounting slots cause angular pulley twist, rapid V-belt wear, high vibration, and belt jumping within 15 hours of operation.
* **The Fixture Solution:**
  - Standard hardened base with locator dowel pins seating against chassis datum corners.
  - Drill guide bushings (hardened alloy steel) precisely locating the 4 slotted motor-mount holes at exact parallel center distance ($\pm 0.2\text{ mm}$).
  - Integrated push-action toggle clamps for rapid 30-second clamping.
  - Eliminated pulley misalignment and reduced chassis hole drilling time by **65%**.

---

## Bill of Materials (BOM)

| Part No. | Component Name | Material | Qty | Manufacturing Process |
| :---: | :--- | :--- | :---: | :--- |
| **W-01** | Curved Weeding Blades (L-Type) | High-Carbon Steel (En45) | 6 | Shearing, Hot Bending, Oil Quenching |
| **W-02** | Main Rotor Drive Shaft | Cold Finished Steel (En8) | 1 | Lathe Turning, Milling Hex Flats, Keyways |
| **W-03** | Blade Mounting Rotor Hub | Mild Steel (C45) | 2 | Turning, 6-Hole PCD CNC Drilling |
| **W-04** | Chassis Structural Frame | Mild Steel Angle (35x35x3 mm) | 1 | Saw Cutting, Jig Clamping, Arc Welding |
| **W-05** | Protective Mudguard Cover | CRCA Sheet Metal (1.6 mm) | 1 | CNC Laser Cutting, Press Brake Bending |
| **W-06** | Engine Drive Pulley (Ø60 mm) | Cast Iron Grade FG 200 | 1 | Turning, V-Groove Machining, Keywaying |
| **W-07** | Driven Rotor Pulley (Ø250 mm) | Cast Iron Grade FG 200 | 1 | Turning, Single V-Groove, Dynamic Balancing |
| **W-08** | V-Belt Transmission | Synthetic Neoprene Rubber | 1 | Standard B-Section Industrial Belt (B-48) |
| **W-09** | Heavy Duty Pillow Block Bearings | Cast Iron Housing (UCP 205) | 2 | Bolt Fastening with Grease Nipples |
| **W-10** | Handlebars & Cross Bracing | Mild Steel Tube (Ø25.4 mm) | 1 | Tube Bending, Rubber Grip Assembly |
| **W-11** | Adjustable Depth Control Skid | Mild Steel Flat (40x5 mm) | 1 | Bending, Slotted Hole Milling |
| **W-12** | Fastener Hardware Kit | High Tensile Steel (Grade 8.8) | 1 Set | Hex Bolts M8 & M10 with Spring Washers |

---

## Manufacturing & Assembly Workflow

```
1. Raw Material Sizing & Stock Preparation (Bandsaw & Shear)
   ├── 2. Blade Hot Forging, Quenching & Hardness Testing (42-45 HRC)
   ├── 3. Shaft Turning, Keyway Milling & Bearing Journals (ISO h6 Fit)
   └── 4. Chassis Frame Fabrication & Drilling Using Custom Jig
          └── 5. Belt-Pulley Transmission Alignment (Parallelism < 0.5 mm)
                 └── 6. Dynamic Vibration & Field Soil Trial Verification
```

---

## Repository Structure

```
├── README.md                           # Main engineering project overview
├── scripts/
│   └── weeder_design_calculations.py   # Kinematics, power, torque & shaft calculations
├── cad/
│   ├── README.md                       # CAD model hierarchy and drafting standards
│   ├── parts/                          # 3D Part models (CATIA V5 / STEP files)
│   ├── assembly/                       # Main product assemblies (.CATProduct / .STEP)
│   └── drawings/                       # 2D Manufacturing drawings with GD&T (.PDF / .DXF)
├── bom/
│   ├── Bill_Of_Materials.csv           # Detailed spreadsheet Bill of Materials
│   └── Bill_Of_Materials.md            # Clean markdown component breakdown
├── jigs-and-fixtures/
│   └── drilling_jig_report.md          # Technical report on motor mount drilling fixture
└── .gitignore                          # Standard CAD, Python, and OS ignore rules
```

---

## How to Run the Calculations

To run the automated mechanical design script:

```bash
# Clone the repository
git clone https://github.com/sawankumar20022-commits/motorized-rotary-weeder-cad.git
cd motorized-rotary-weeder-cad

# Run calculation script (Requires Python 3.x)
python scripts/weeder_design_calculations.py
```

**Sample Output:**
```text
============================================================
 MOTORIZED ROTARY WEEDER: MECHANICAL DESIGN AUDIT
============================================================
Rotor Sweep Diameter:         220.00 mm
Rotor Operating Speed:        260.00 RPM
Blade Tip Linear Velocity:    2.99 m/s
Motor Power:                  1.50 kW (2.01 HP) @ 2400 RPM
V-Belt Reduction Ratio:       9.23 : 1
------------------------------------------------------------
[RESULT] Soil Cutting Torque: 50.14 N.m
[RESULT] Minimum Shaft Dia:   18.2 mm (Actual selected: 25.0 mm, FOS = 2.6)
[RESULT] Field Capacity:      0.08 ha/hr (Inter-row weeding speed)
============================================================
STATUS: MECHANICAL DESIGN AUDIT PASSED - SAFE FOR MANUFACTURE
```

---

## Author & Academic Context

* **Engineer:** Sawan Kumar
* **Degree:** B.Tech in Agricultural Engineering (Central Agricultural University) | M.Tech in Ophthalmic Engineering (IIT Hyderabad)
* **Specialization:** Farm Machinery & Power Engineering, Machine Elements, CAD (CATIA V5), Production Tooling
* **GitHub:** [sawankumar20022-commits](https://github.com/sawankumar20022-commits)
* **Contact:** op25mtech11005@iith.ac.in | [LinkedIn](https://linkedin.com/in/sawan-kumar)

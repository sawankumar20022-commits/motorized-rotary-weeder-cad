# CATIA V5 CAD Modeling & 2D Drafting Hierarchy

This directory contains the 3D parametric models, mechanical assemblies, and 2D engineering drafting sheets for the **Motorized Rotary Weeder Mechanism**.

---

## Directory Organization

```
cad/
├── parts/               # Native CATIA V5 Parts (.CATPart)
├── assembly/            # Main Mechanical Assemblies (.CATProduct)
├── drawings/            # 2D Manufacturing Drafting Sheets with GD&T (.CATDrawing / .PDF)
└── exports/             # Neutral 3D CAD Exchange Formats (.STEP / .DXF)
```

---

## 1. Native Part Models (`cad/parts/`)
* `W01_Curved_Weeding_Blade.CATPart` — Hot forged En45 spring steel L-blade.
* `W02_Rotor_Hex_Drive_Shaft.CATPart` — Ø25 mm turned and keyed shaft.
* `W03_Blade_Mounting_Hub.CATPart` — 6-hole circular flange mounting.
* `W04_Structural_Angle_Chassis.CATPart` — Welded 35x35 mm frame structure.
* `W05_Protective_Mudguard.CATPart` — 1.6 mm sheet metal safety cover with bend reliefs.
* `W06_Locating_Drilling_Jig_Plate.CATPart` — Custom tooling plate with hardened drill bushings.

---

## 2. Assembly Models (`cad/assembly/`)
* `Rotary_Weeder_Main_Assembly.CATProduct`
  * `SubAssy_Rotor_Cutter_Unit.CATProduct` (Shaft + Flanges + 6 Blades + Bearings)
  * `SubAssy_Power_Transmission.CATProduct` (Engine + Pulleys + V-Belt)
  * `SubAssy_Chassis_Handlebars.CATProduct` (Frame + Depth Skid + Mudguard)

---

## 3. 2D Drafting Standards (`cad/drawings/`)
* All drawings comply with **ISO 128 / ASME Y14.5** drafting rules:
  * **Projection:** 1st Angle Projection.
  * **Shaft Fits:** ISO **h6/H7** on bearing journals.
  * **Geometric Tolerancing (GD&T):** Parallelism $\mathbin{/\!/} 0.2\text{ mm}$ between motor mount slots and rotor axis.
  * **Title Blocks:** Material specification, standard surface roughness ($\text{Ra } 1.6\,\mu\text{m}$ on journals), revision status.

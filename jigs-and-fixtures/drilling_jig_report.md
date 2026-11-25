# Engineering Tooling Report: Motor Mount Locating & Drilling Jig Design

**Author:** Sawan Kumar  
**Target Mechanism:** Motorized Rotary Weeder Chassis & Motor Mount Fabrication  
**CAD Platform:** CATIA V5  
**Core Competency:** Jig & Fixture Tooling, GD&T, Parallelism Control, Process Improvement  

---

## 1. Manufacturing Challenge & Problem Statement
During prototype assembly of the motorized rotary weeder, manually marking and hand-drilling the 4 slotted mounting holes for the 1.5 kW engine/motor resulted in severe alignment defects:
* Center-to-center parallelism between the motor drive pulley and driven rotor pulley deviated by **up to 2.8 mm across a 400 mm span**.
* This angular twist caused excessive V-belt edge scuffing, vibration, and premature belt throwing under high soil cutting loads.
* Manual marking and filing of slotted holes consumed **45 minutes per chassis frame** with high scrap rates.

---

## 2. Jig Design Principles (3-2-1 Locating System)

To guarantee exact pulley coplanarity and hole positional accuracy, a dedicated **Workbench Locating & Drilling Jig** was designed in CATIA V5:

```
                  [ Push-Action Toggle Clamp ]
                                │
                                ▼
[ Hardened Drill Bushing Plate ] ──▶ [ Hardened Stop Pins (2-Point Datum) ]
                                │
                                ▼
             [ Chassis Base Angle Frame (Rest Pads) ]
```

1. **Primary Datum (3 Points):** Hardened ground flat rest pads supporting the lower face of the chassis angle frame to constrain vertical degree of freedom.
2. **Secondary Datum (2 Points):** Hardened vertical guide pins locating against the machined outer edge of the chassis frame.
3. **Tertiary Datum (1 Point):** Precision transverse end stop establishing the exact center distance from the rotor bearing mounting holes.

---

## 3. Tooling & Guidance Features
* **Hardened Drill Guide Bushings:** Press-fit carbon steel alloy bushings (heat-treated to 58–62 HRC) prevent drill bit wandering and ensure perpendicular hole entry.
* **Slot Milling Guide Inserts:** Guided pilot holes spaced to allow clean slot elongation with an end mill without manual filing.
* **Quick-Acting Toggle Clamps:** Robust push-action manual clamps secure the chassis firmly in 15 seconds.
* **Chip Clearance Relief:** Engineered chip evacuation channels under the bushing plate prevent metal swarf build-up from altering the locating datum.

---

## 4. Production Results & Quality Verification (Kaizen)

| Parameter | Manual Marking & Drilling | With CATIA V5 Locating Jig | Improvement |
| :--- | :---: | :---: | :---: |
| **Pulley Parallelism Error** | $2.8\text{ mm}$ twist | $< 0.2\text{ mm}$ deviation | **92% accuracy improvement** |
| **Chassis Drilling Cycle Time** | 45 minutes | 8 minutes | **82% cycle time reduction** |
| **V-Belt Operational Life** | ~20 hours (premature wear) | > 250 hours (standard rating) | **12x durability gain** |
| **Assembly Re-work Rate** | 30% frames required shimming | 0% shimming required | **Zero assembly rework** |

---

## 5. Conclusion
This locating and drilling jig solved the root cause of V-belt vibration and misalignment. It demonstrates how simple, rigid production tooling turns complex manual fitting into a fast, repeatable manufacturing process.

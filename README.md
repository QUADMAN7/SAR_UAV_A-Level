# Autonomous SAR UAV Airframe
A custom 1.5m wingspan SAR UAV—fully 3D-printed as an A-Level Design & Technology project (Awarded Grade A*).

<img width="4032" height="3024" alt="20240328_132211" src="https://github.com/user-attachments/assets/f9c1c8da-cc8d-444f-ac9b-df000500090b" />


## 📌 Overview
The SAR Fixed-Wing UAV is a 1.5m wingspan autonomous airframe engineered for Search & Rescue (SAR) operations. Designed as part of my A-Level Design & Technology engineering project. The platform features a pusher-propeller configuration, internal avionics bay, full autonomous capabilities and a forward FPV navigation camera. This project was inspired by the zipline drone company who specialise in rapid delivery of critical medical supplies to hospitals in Rwanda but I aimed to serve the slightly different purpose of using a UAV platform to aid search and rescue missions in large areas; something the usual multirotor setups aren't fully capable of.
 
* **Timeline:** Sep 2022 – Jun 2024  
* **Key Tools:** Fusion 360, ArduPilot, Mission Planner, LW-PLA, OrcaSlicer 

---

## ⚙️ Technical Specifications

| Parameter | Specification |
| :--- | :--- |
| **Wingspan** | 1.5 m |
| **Wing Area ($S$)** |0.2981 m² |
| **Main Wing Aerofoil** | NACA 2412 |
| **All-Up Mass (AUW)** | 2.43 kg |
| **Wing Loading** | 81.5 g/dm² |
| **Wing Cube Loading** | 14.9 |
| **Stall Speed ($V_{\text{stall}}$)** | 18 m/s |
| **Flight Controller** | Holybro Durandal (ArduPilot) |
| **Propulsion Setup** | 6S LiPo, Folding 13" Pusher Propeller |

---

## ⚙️ Key Engineering Features

* **Custom Fuselage Geometry:** Engineered an organic outer shell shape with an internal volume for avionics, battery, and rear pusher motor mounting, leaving central volume open for a future payload drop bay.
* **Serviceability & Access:** Designed hatches and external service doors into the airframe for rapid field replacement of electronics, linkages, and control surface servos.
* **Avionics Stack:** Configured for full wireless telemetry, FPV video link, and multi-sensor navigation via ArduPilot.

---

## 🏗️ Construction & Manufacturing Method

The airframe was manufactured using a hybrid 3D-printing and epoxy-reinforcement technique designed to maximize the strength of the LW-PLA airframe whilst simultaneously keeping the weight to a minimum.

* **3D Printing & Resin Coating:** Airframe printed in sections using Lightweight PLA (LW-PLA). To drastically improve inter-layer shear strength and structural rigidity, the outer skin was coated in multiple coats of **Easy Composites XCR Epoxy Coating Resin**.
* **Structural Alignment & Joint Bonding:** The fuselage sections were aligned using 2mm steel wire registration pins to ensure precise aerodynamic geometry, then permanently bonded using the XCR resin matrix.
* **Kinematics & Fasteners:** Control surfaces utilize 2mm steel wire pin hinges for slop-free movement. All hatches, access covers, and servo mounts are secured using M3 heat-set brass inserts and machine screws for reliable field maintenance.
* **Finishing & Stencilling:** The airframe underwent a multi-stage post-processing workflow: hand-sanding, priming, multiple coats of orange paint, and custom stencilled airframe lettering using paper negatives. Unfortunately, some of the lettering suffered from paint bleeding under the paper stencil resulting in poor lettering in some places.
* **Systems Integration:** Final integration included full wire routing, power distribution, sensor mounting, and ArduPilot flight controller calibration.

---

## ⚠️ Engineering Challenges & Iterations

### 1. High fuselage weight and limited accessibility to internals
* **Problem:** The first iteration of the LW-PLA printed fuselage resulted in an all-up weight of roughly 800g and offered limited accessibility to the internals of the fuselage for installing electronics and servicing other internal components like the avionics mounting plate.
* **Second Iteration Solution:** The whole fuselage was redesigned to have two extra hatches to access the internals (battery, flight controller and ESC) and steps to reduce weight were taken. These steps included reducing infill and perimeter walls, and removing material in CAD where material was not required such as the plates for mounting the avionics.
* **Key Manufacturing Takeaway:** Unfortunately the removal of material in CAD did not yield the weight gains I was hoping for. Physical testing revealed an invaluable additive manufacturing constraint: cutting small holes in CAD often increases weight because perimeter walls (dense plastic) replace light-weight interior infill. While the second iteration ended up slightly heavier after post-processing, it vastly improved on the internal serviceability and structure of the first iteration.

### 2. The LW-PLA trial
* **Problem:** Ideally, to make a light-weight airframe using LW-PLA you would use the slicing technique called 'Vase Mode'. When I began this project, I made multiple attempts to create the design in CAD in such a way that I could use Vase Mode but due to the complex geometries I was working with, the fact that I had never made a model plane from LW-PLA before and I was running out of time to complete the CAD phase of this project, I had to come up with an alternative design method.
* **Solution:** I was forced to abandon the Vase Mode technique and stick with traditional discreet layers and infill which resulted in a lot of extra filament begin used and a lot more time post processing than would have otherwise been necessary but it is a technique I am very familiar with and was able to adapt for the use case.

### 3. Control Surface Under sizing & CAD Scale Discrepancy
* **The Problem:** Designing exclusively in 3D CAD without physical scale reference points resulted in undersized control surfaces, posing a high risk of insufficient aerodynamic control authority (sluggish pitch and roll response).
* **Solution:** Physical evaluation of the first 3D-printed prototype immediately identified the scale error prior to flight testing. I returned to CAD to redesign enlarged control surfaces with significantly increased chord length and surface area to guarantee positive control authority.

### 4. High Stall Speed & Launch Risk
* **The Problem:** Mass budget underestimates during initial CAD modelling resulted in an All-Up Weight (AUW) of 2.43 kg and excessive wing loading. Sizing calculations yielded an 18 m/s stall speed ($V_{\text{stall}}$), making hand-launching nearly impossible due to immediate stall risk.
* **Solution:** While the pure aerodynamic fix requires increasing wing area and selecting a higher $C_{L,\max}$ aerofoil, the operational issue was solved by offloading launch acceleration to external Ground Support Equipment (GSE). A separate launch trolley was designed to bring the UAV up to flying speed without adding heavy onboard landing gear to the airframe.
---

## 📁 Repository Structure

```text
├── Docs/             # 2D engineering drawings (PDF)
└── Media/
    ├── 01_Designing/ # Hand sketches, sizing trade studies, concept iterations
    ├── 02_CAD/       # High-res assembly renders, section views, exploded views
    ├── 03_Construction/     # 3D printing process, resin coating, wire routing, painting
    └── 04_Final Product/     # Completed airframe photos, beauty shots, ground test clips

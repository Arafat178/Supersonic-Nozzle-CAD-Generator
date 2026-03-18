# Supersonic Nozzle CAD Generator

A fully integrated **engineering + CAD automation tool** that bridges **compressible flow theory** with **real-world SolidWorks geometry generation**.

This project transforms thermodynamic inputs into a **parametric supersonic nozzle design**, visualizes the contour, and automatically generates a **ready-to-run SolidWorks VBA macro**.

---

## Key Features

 * **Physics-Based Design**

  * Isentropic flow relations
  * Mach number calculation from pressure ratio
  * Area ratio (Ae/At) computation
  * Real throat & exit geometry

*  **Interactive Visualization**

  * Smooth nozzle contour using cubic polynomial interpolation
  * Real-time 2D plotting with Plotly

*  **CAD Automation**

  * Auto-generated **SolidWorks VBA Macro**
  * Creates:

    * Spline-based nozzle profile
    * Revolved 3D geometry
    * Shell operation for thickness

*  **Parametric Control**

  * Fully adjustable:

    * Chamber pressure & temperature
    * Mass flow rate
    * Gas properties (γ, R)
    * Exit pressure
    * Nozzle length & thickness

---

##  Engineering Core

The design is based on **isentropic compressible flow equations**:

* Throat Area:

  Aₜ = (ṁ √(R T₀)) / (P₀ √γ) * ((γ+1)/2)^((γ+1)/(2(γ−1)))

* Exit Mach Number:

  Mₑ = √[(2/(γ−1)) ( (P₀/Pₑ)^((γ−1)/γ) − 1 )]

* Area Ratio:

  Aₑ/Aₜ = (1/Mₑ) * [ (2 + (γ−1)Mₑ²)/(γ+1) ]^((γ+1)/(2(γ−1)))

---

##  Nozzle Geometry Logic

The nozzle contour is generated using a **smooth cubic polynomial transition**:

* Converging section → throat
* Throat → diverging section

Equation form:

y = y₁ + (y₂ − y₁)(3t² − 2t³)

This ensures:

* Smooth slope (no shock-inducing discontinuity)
* Manufacturable geometry
* CAD-friendly spline generation

---

##  Tech Stack

* **Frontend:** HTML, CSS, JavaScript
* **Visualization:** Plotly.js
* **CAD Automation:** SolidWorks VBA
* **Engineering Model:** Compressible Flow Theory

---

##  How to Use

1. Open the HTML file in your browser:

   ```
   Nozzle2.html
   ```

2. Input your design parameters:

   * Chamber Pressure (P₀)
   * Temperature (T₀)
   * Mass Flow Rate (ṁ)
   * Exit Pressure (Pₑ)
   * Geometry constraints

3. Click:

   ```
   Calculate & Generate
   ```

4. Copy the generated **VBA Macro**

5. Open **SolidWorks → VBA Editor**

   * Paste the macro
   * Run it

6.  Your **3D nozzle model** is generated automatically

---

##  Output

* ✅ Nozzle contour plot
* ✅ Engineering parameters
* ✅ SolidWorks-ready macro
* ✅ 3D revolved model

---

## ⚠️ Limitations

* Assumes **ideal isentropic flow**
* No shock modeling or viscous effects
* Fixed polynomial contour (not Rao optimized)

---

##  Future Improvements

* 🔬 Rao bell nozzle optimization
* 🌡️ Real gas effects
* 🧮 CFD integration (ANSYS / OpenFOAM)
* 🧱 Mesh generation export
* ☁️ Web-based CAD export (STEP/STL)

---



## Author

**Arafat Hossain** Mechanical Engineering Student

---


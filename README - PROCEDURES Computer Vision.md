# Computer-Vision-for-Fire-Mod

My VS Code Computer Vision Updates for analysing wildfire spread within Minecraft.

---

## 🔥 Project Overview

This repository processes and analyses screenshots from Minecraft wildfire simulations to produce:

* **Classification Animations** for fire spread and persistence visualisation.
* **Arrival Time Matrices** for each grid cell ignition.
* **Rate of Spread (ROS)** plots along 4 diagonals.
* **Heat Maps** and **Isochrone Contours** to visualise spatio-temporal fire spread.

The classification pipeline mimics FARSITE-style output and supports real-time fire spread modelling within Minecraft.

---

## 📁 Folder Structure

```bash
Computer-Vision-for-Fire-Mod/
│
├── Media/                      # Videos and image outputs for presentation
│   ├── MODIFIED_V1.mp4        # Modified fire model classification animation
│   ├── DEFAULT_V2.mp4         # Default fire model classification animation
│   └── Classification Image - Original vs Modified.svg
│
├── Input/                     # Raw screenshot sequences for analysis
│   ├── 1_Classification/      # Used for colour classification animation ONLY (no ROS)
│   ├── 2_Arrival_Matrix/      # Prepares arrival time matrices (using classified frames)
│   ├── 3_Analysis/            # Smooth isochrones, heatmaps, and ROS calculation
│
├── AVERAGED Arrival Matrices/ # Stores .npy matrices of averaged arrival times
│
├── Create Arrival Time Matrices.ipynb
├── Averager and Heat Map & Smooth Isochrone Plotter.ipynb
├── Diagonal Rate of Spread Calculator.ipynb
└── Fire Spread Tracking - Classification Images.ipynb
```

---

## 🧪 How to Use the Jupyter Notebooks (In Order)

### 1. **Classification Only (Standalone Visualisation)**

Use this *only* if you want to produce animations and classified grids from screenshots.

📄 `Fire Spread Tracking - Classification Images.ipynb`

* Converts screenshots into grid-based fire spread classification.
* **Outputs:** animated `.mp4` files and classified `.png` frames.
* **No ROS / no timing** – this is visual-only and not used in further numerical analysis.

---

### 2. **Generate Arrival Time Matrices**

🧩 `Create Arrival Time Matrices.ipynb`

* Loads the classified `.png` images from the fire spread simulation.
* Extracts the fire arrival time per grid cell.
* Saves output as `.npy` matrix files in `AVERAGED Arrival Matrices/`.

---

### 3. **Plot Isochrones & Heat Maps**

🎯 `Averager and Heat Map & Smooth Isochrone Plotter.ipynb`

* Loads `.npy` files from Step 2.
* Produces:

  * Smoothed **isochrones**
  * **Arrival-time heat maps**
  * **Overlay visualisations**
* Automatically saves plots for each test case.

---

### 4. **Diagonal ROS Calculator**

📈 `Diagonal Rate of Spread Calculator.ipynb`

* Takes `.npy` arrival matrices from Step 2.
* Calculates rate of spread (ROS) along:

  * NW, NE, SW, SE diagonals.
* Outputs a CSV (if `SAVE_CSV = True`) for summary.

---

## 🧠 Notes

* Always run files **in order: 2 → 3 → 4** for arrival time and ROS analysis.
* Only use the `1_Classification` notebook as a **standalone** tool if animation is your sole goal.
* All notebooks are designed to work on standard laptops and avoid specialist software dependencies.

---

## 📽️ Media Outputs

### 🔧 Modified Version

[Watch MODIFIED\_V1 Video](Media/MODIFIED_V1.mp4)

### 🧱 Default Version

[Watch DEFAULT\_V2 Video](Media/DEFAULT_V2.mp4)

---

## 🔍 Classification Comparison

![Original vs Modified Classification Image](Media/Classification%20Image%20-%20Original%20vs%20Modified.svg)

---

Let me know if you want this in `markdown` format to copy directly, or if you'd like me to create a downloadable file.


# Hamina Map Exporter Pro

This tool provides a professional way to export high-resolution Access Point (AP) placement maps from **Hamina Wireless** project data. It solves the common issue of icons being too small or hard to read on large floor plans by allowing custom scaling and smart PDF reconstruction.

---

## 🚀 Tool Versions

This repository contains two specialized tools to fit different documentation workflows:

### 1. Quick Image Exporter (`HaminaReport.html`)
Designed for users who only need individual, high-resolution image files (`.png`) for installation guides or 3rd-party documentation.
* **Live Preview Scaling:** Adjust icon sizes with a slider and see the result instantly.
* **Per-Floor Overrides:** Make icons larger on massive warehouses but smaller on office floors within the same project.
* **Batch Export:** Generates a ZIP file containing all processed maps with correct naming conventions.

### 2. Advanced Report Generator (`HaminaReportExport.html`)
Designed for users who want to modify an existing **Hamina PDF Report** into a professional, site-ready document.
* **Smart OCR Range Detection:** Automatically scans your PDF Table of Contents to find specific sections like the *Bill of Materials* or *AP Notes*.
* **Dynamic Page Formatting:** * Enlarges technical pages (like BoM tables) to **A3 Landscape** for better readability.
    * Enforces standard **A4 Portrait** for the rest of the text.
* **AP Placement Replacement:** Deletes low-resolution placement pages from the original Hamina report and appends your new, custom-scaled **A1 high-res maps**.
* **Fidelity Preservation:** Edits the PDF in-place to ensure 100% of original fonts, backgrounds, and vector quality are kept.

---

## 🛠 How to Use

### Step 1: Export Project Data from Hamina
1.  Open your project in **Hamina Wireless**.
2.  Click **Actions** and select **Export OpenIntent JSON**.
3.  Ensure you download the `.zip` version, which contains both the project logic and the raw floor plan images.

### Step 2: Load the Tool
1.  Open either `HaminaReport.html` or `HaminaReportExport.html` in any modern web browser (Chrome, Edge, or Safari).
2.  Upload your OpenIntent `.zip` file.
3.  *(Optional for Advanced version)*: Upload the original Hamina `.pdf` report.

### Step 3: Adjust Scaling
1.  Use the **Global Icon Scale** slider to change the size of the "teardrop" AP icons across all floors.
2.  Use the **Override** slider on specific map preview cards to fine-tune icon sizes for different floor types.
3.  Icons mimic the official Hamina style, including color coding and rotation/azimuth pointers.

### Step 4: Map Mapping (Advanced Version Only)
1.  Click **🔍 Auto-Detect Ranges from TOC**. The tool will guess which pages to enlarge to A3 and which to delete.
2.  Verify the ranges:
    * **A3 Landscape Pages:** Typically *Bill of Materials*, *Notes and Zones*, and *AP Notes*.
    * **Pages to Delete:** The original *AP Placement* section.

### Step 5: Export
1.  Click **Download High-Res ZIP** for individual images.
2.  Click **Generate Updated PDF Report** to receive a unified document with corrected page sizes and high-resolution A1 maps.

---

## 💡 Technical Notes
* **No Server Uploads:** All processing happens locally in your browser. Your project data and floor plans never leave your computer.
* **Memory Safety:** When generating massive A1 maps, the tool processes images sequentially to prevent browser crashes on high-resolution assets.
* **Coordinate Precision:** Uses pixel-perfect mapping from the `openIntent.json` file to ensure APs are exactly where they were placed in the design.

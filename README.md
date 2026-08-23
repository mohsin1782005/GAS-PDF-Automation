# 📄 Dynamic KPI Reporting Engine & PDF Automation Factory

![Google Sheets GAS Automation](Google_Sheets_Automation(GAS).png)

A production-ready **Google Apps Script (GAS)** automation engine that generates pixel-perfect, branded PDF reports on demand directly from Google Sheets. Features active row detection, custom UI menu buttons, template variable replacement, and automatic Google Drive file delivery with backlink synchronization.

---

## 🚀 Key Features

* **Active Row Context Detection:** Automatically determines the user's cursor position in the spreadsheet to process target records with zero manual input parameters.
* **Dynamic Template Interpolation:** Replaces double-bracket placeholders (`{{Client_Name}}`, `{{Date}}`, `{{Price}}`, `{{Comments}}`) inside a master Google Doc template with live cell values.
* **Automated Blob Conversion & Drive Archiving:** Converts intermediate Google Docs into finalized PDF blobs and organizes them inside a dedicated Google Drive folder structure.
* **Bi-Directional Link Logging:** Captures the newly generated PDF shareable URL and writes it back to the corresponding spreadsheet row for instant team access.
* **One-Click Execution UI:** Embedded UI button triggering backend execution without opening script editors.

---

## 🛠️ Tech Stack & Workspace APIs

* **Core Runtime:** `Google Apps Script (JavaScript ES6)`
* **Data Layer:** `SpreadsheetApp` (Data extraction, active range detection, URL logging)
* **Document Manipulation:** `DocumentApp` (Template cloning, body token replacement)
* **File Management & Export:** `DriveApp` (Folder routing, doc-to-PDF blob rendering)
* **Formatting:** `Intl Currency Formatting & Date Parsing`

---

## 📐 Automation Workflow Architecture

[User Row Selection] ➔ [Click "GENERATE REPORT" Button] ➔ [SpreadsheetApp: Extract Row Values] ➔ [DriveApp: Clone Master Doc Template] ➔ [DocumentApp: Regex Token Replacement] ➔ [DriveApp: Export PDF Blob & Save] ➔ [SpreadsheetApp: Write PDF URL to Column F]

---

## ⚙️ How to Setup & Deploy

1. **Setup Google Drive Structure:**
   * Create a master template document in Google Docs with your target placeholders (e.g., `{{Client Name}}`, `{{Price}}`, `{{Date}}`).
   * Create a designated destination folder for generated PDFs in Google Drive.
2. **Add Script to Sheet:**
   * In your Google Sheet, navigate to **Extensions** $\rightarrow$ **Apps Script**.
   * Paste the script from `Code.gs` in this repository.
   * Replace `TEMPLATE_DOC_ID` and `DESTINATION_FOLDER_ID` with your respective Google Drive IDs.
3. **Assign UI Button:**
   * Insert a drawing/button into the Sheet (**Insert** $\rightarrow$ **Drawing**).
   * Click the 3 dots on the drawing $\rightarrow$ **Assign script** $\rightarrow$ enter `generatePdfFromActiveRow`.
4. **Authorize & Execute:** Select any row (Row 2+) and click your button to generate reports.

---

## 📄 License
This project is licensed under the [MIT License](LICENSE).

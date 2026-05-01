# Dynamic KPI Reporting Engine & PDF Automation Factory
A professional Google Apps Script engine that automates PDF report generation from Google Sheets. Features active row detection, custom UI buttons, and dynamic data injection into branded Doc templates. Designed for high-efficiency business workflows and KPI reporting automation.

## Project Overview
Manual report generation is time-consuming and prone to human error. This "PDF Factory" allows a user to select any record from a spreadsheet and instantly generate a formatted PDF document using a custom Google Doc template.

### Key Features
Active Row Detection: Automatically identifies which row the user has selected, enabling specific report generation without manual inputs.
Dynamic Data Injection: Uses placeholder mapping ({{Tag}}) to swap template variables with real-time sheet data.
Automated Workflow: Handles file creation, PDF conversion, and directory organization within Google Drive.
One-Click Interface: Features a custom-designed floating action button within Google Sheets for a seamless user experience.

## Technical Architecture
### 1. Data Source (Google Sheets)
The engine processes a structured dataset containing:
Client Name: Primary identifier.
Date: Record timestamp.
Price: Financial data (formatted via script as currency).
Status: Project lifecycle stage.
Comments: Detailed qualitative notes from Column E.

### 2. The Engine (Google Apps Script)
The backend logic is written in JavaScript and utilizes the following Google Workspace services:

SpreadsheetApp: To retrieve active cell data and write back generated links.
DocumentApp: To manipulate the Google Doc template and perform text replacement.
DriveApp: To manage folder structures and convert document "blobs" into final PDF files.

### 3. Professional Output (PDF)
The final output is a branded, professional PDF saved directly to a designated "Generated PDFs" folder. The script then captures the file URL and logs it back to the original spreadsheet for instant access.

## How to Use
Select a Row: Click on any cell in the row you wish to generate a report for (Row 2 or below).
Click "GENERATE REPORT": Press the custom blue button on the dashboard.
Access PDF: Once the success alert appears, click the link that was automatically added to Column F.

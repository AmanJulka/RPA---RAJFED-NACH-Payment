## 🌾 RAJFED NACH Payment Automation: File Conversion & UTR Update 🚀

###  Streamlining Farmer Payments for RAJFED with Automated NACH File Processing 🏦 - Saving **30 Minutes Daily** and Enhancing Payment Tracking!

This project automated the manual process of converting RAJFED (Rajasthan State Cooperative Marketing Federation Ltd) payment files to YES Bank (YBL) format and updating them with UTR (Unique Transaction Reference) numbers for NACH (National Automated Clearing House) payments to farmers.  The solution saves **30 minutes of manual effort daily**, streamlines payment processing, and ensures accurate UTR tracking for efficient reconciliation.

### 🎯 Requirement: Manual File Conversion and UTR Updates for Client Payments

The existing process for RAJFED payments presented these challenges:

*   **😓 Incompatible Client File Format:** RAJFED provided payment files in a non-standard XLSX format, incompatible with YES Bank's YBL format required for NACH processing.
*   **⏱️ Manual File Conversion:** CSD (Customer Service Desk) team had to manually convert RAJFED's XLSX files into the YBL format, a time-consuming and repetitive task.
*   **🔄 Manual UTR Number Updates:**  After payment processing, UTR numbers were provided separately and had to be manually updated back into the original RAJFED file for reconciliation and tracking.
*   **⚠️ Risk of Manual Errors:** Manual file conversion and UTR updates were prone to human errors, potentially leading to payment discrepancies or reconciliation issues.
*   **⏳ Time Delay in Payment Processing:**  Manual file handling added delays to the overall payment processing cycle.

### 🤖 Automation Approach: Two-Stage Automation for File Conversion and UTR Enrichment

Our automation strategy implemented a two-stage approach to handle the RAJFED payment processing requirements:

*   **Stage 1: File Conversion & Working File Preparation**
    *   **📥 Automated Input File Pickup:** 🤖 Bot automatically picks up the RAJFED input file (XLSX format) placed by the user in a designated **"Input" shared drive folder**.
    *   **💾 Temporary Database Table Creation:** 🤖 Bot dynamically creates a **temporary database table** to store the payment records for efficient processing within the automation workflow. This table is automatically dropped at the end of the day (EOD) for data hygiene.
    *   **🛠️ Working File Generation with Unique Reference Key:** 🤖 Bot generates a **"Working File"** containing the payment data in a structured format. This file includes two key new columns: **"Unique Reference No."** (initially populated) and **"UTR No."** (initially blank).
    *   **🔑 Unique Reference Number Generation:** 🤖 Bot automatically populates the **"Unique Reference No."** column by concatenating key fields from the input file: **Amount + Message Type + Beneficiary Account Number + Beneficiary Name + Beneficiary IFSC**. This unique key is crucial for linking records during the UTR update stage.
    *   **🗺️ Field Mapping & YBL Format Conversion:** 🤖 Bot performs **intelligent field mapping** to convert the RAJFED input file data into the required **YBL (YES Bank Limited) payment file format**, ensuring compatibility with YES Bank's payment systems.
    *   **📤 "Uploadable File" and "Output File" Generation:** 🤖 Bot generates two output files and saves them in designated shared drive folders:
        *   **"Uploadable File" (.xls/.xlsx) in "Process" Folder:** This file, now in YBL format, is ready for manual upload into YES Bank's Newgen application for payment initiation.  Duplicate records are automatically excluded during this file preparation.
        *   **"Output File" (.xls/.xlsx) in "Output" Folder:** This file, structurally similar to the "Uploadable File," is likely intended as an interim output or backup. *(Note: Clarification needed if "Uploadable" and "Output" files are truly distinct)*

*   **Stage 2: UTR Number Update and Final Output**
    *   **📥 Input File Pickup from "Process" Folder:** 🤖 Bot picks up the **"Working File"** (generated in Stage 1 and located in the "Process" folder).
    *   **📥 UTR File Pickup (User Provided) from "Process" Folder:** 🤖 User manually places a **second file (format not explicitly specified, but assumed to contain UTR numbers)** in the **"Process" folder** alongside the "Working File." This second file contains the UTR numbers provided after payment processing.
    *   **🔄 UTR Number Update:** 🤖 Bot reads the UTR numbers from the user-provided file and **updates the "UTR No." column in the "Working File"** (using the "Unique Reference No." as the key for matching records).
    *   **📤 Final Updated File in "Output" Folder:** 🤖 Bot saves the **final updated file (now containing UTR numbers)** in the **"Output" folder** within the shared drive. This final output file, in RAJFED's original format but enriched with YBL-converted data and UTR numbers, is then accessible to the user.

### ✨ Role of Automation: Bridging File Format Incompatibility and Streamlining UTR Tracking

Automation played a vital role in overcoming file format challenges and enhancing payment process visibility:

*   **Automated File Conversion:** 🤖 Bot automatically handles the complex file format conversion from RAJFED's format to YBL format, eliminating manual conversion effort and ensuring compatibility.
*   **Streamlined UTR Update Process:** 🔄 Automation significantly simplifies the UTR update process, automatically merging UTR numbers into the RAJFED payment file using a robust linking mechanism (Unique Reference Number).
*   **Reduced Manual Data Handling:** 📉 Bot minimizes manual data manipulation and eliminates the need for users to manually prepare files or update UTR numbers.
*   **Improved Data Accuracy:** 💯 Automated file conversion and UTR updates reduce the risk of human errors, ensuring more accurate payment data and reconciliation.
*   **Faster Payment Processing Cycle:** ⏱️ Automation streamlines file processing, contributing to a faster overall payment cycle for RAJFED farmer payments.

### 🚀 Benefits Achieved:  Time Savings, Streamlined Workflow, and Enhanced Accuracy

The RAJFED NACH Payment Automation delivered tangible benefits:

*   **⏱️ 30 Minutes of Daily Time Savings:** Automation saves approximately **30 minutes of manual work per day** for the CSD team, freeing up valuable time for other tasks.
*   **🚀 Streamlined Payment Processing Workflow:** Automation streamlines the entire RAJFED payment file processing workflow, from initial file intake to final UTR-updated output.
*   **✅ Enhanced Data Accuracy & Reduced Errors:** Automated file conversion and UTR updates minimize the risk of manual errors, ensuring higher data accuracy and payment reliability.
*   **🎯 Improved Efficiency & Resource Utilization:** Automation improves the efficiency of payment operations and optimizes resource utilization by reducing manual workload.
*   **📊 Better UTR Tracking & Reconciliation:** Automated UTR updates ensure accurate and timely tracking of UTR numbers within the RAJFED payment file, facilitating easier reconciliation and audit trails.

### 🛠️ Technologies Used:

*   **RPA Tool:** Process Studio (AutomationEdge)
*   **Data Manipulation:** Excel File Automation, Data Mapping & Transformation
*   **Database:** Temporary Database Table Creation & Management (Likely within RPA platform or integrated DB)
*   **File System Automation:** Shared Drive Integration (Input, Process, Output Folders)

### 🎉 Conclusion:  Client-Centric Payment Automation - Delivering Efficiency and Accuracy for RAJFED Farmer Payments!

The RAJFED NACH Payment Automation project demonstrates RPA's capability to address client-specific file format challenges and streamline critical payment processes. By automating file conversion and UTR updates, the solution delivers significant time savings, enhances data accuracy, and improves the efficiency of RAJFED farmer payments, showcasing a client-centric approach to automation and delivering tangible value to both YES Bank and its valued client, RAJFED.

# 🤖 HR Offer Letter Automation using UiPath

## 📌 Executive Summary

This project automates the generation of HR offer letters using UiPath's Robotic Process Automation (RPA) platform. Built on the robust Dispatcher-Performer architecture within the REFramework, the solution minimizes manual effort, ensures document consistency, and streamlines the onboarding workflow.

---

## 🚀 Project Overview

### 🎯 Purpose

Automate the generation of personalized offer letters for newly hired candidates, enhancing efficiency and standardization in HR operations.

### 🏗️ Architecture

- **Dispatcher**: Extracts candidate data from Excel and queues them.
- **Performer**: Processes each queue item to generate offer letters in DOCX and PDF formats.

### 🔧 Technologies Used

- UiPath Studio `v25.0.161.0`
- UiPath REFramework
- Microsoft Excel & Word Integration
- UiPath Orchestrator (Assets & Queues)

---

## ⚙️ Detailed Component Analysis

### 1️⃣ Dispatcher Module

#### ✅ Functionality
- Reads candidate data from Excel.
- Filters hired candidates.
- Creates and logs queue items.

#### 📂 Key Components
- `Main.xaml`: Controls the dispatching logic.
- Try-Catch for error handling.
- Reads `ExcelPath_OfferLetter` from assets.

---

### 2️⃣ Performer Module

#### ✅ Functionality
- Retrieves queue items.
- Opens and populates Word templates.
- Saves documents in DOCX and PDF formats.
- Updates transaction statuses.

#### 🔄 State Machine Flow
- **Init**: Load config and assets.
- **Get Transaction Data**: Fetch queue items.
- **Process Transaction**: Generate offer letters.
- **End Process**: Cleanup and close apps.

#### 📂 Key Components
- `Main.xaml`, `Process.xaml`
- REFramework support workflows
- Exception handling and logging

---

## 🧪 Testing Framework

- `Tests/RunAllTests.xaml`: Executes all tests
- Categorizes Business vs. System exceptions
- Logs pass/fail status with reporting templates

---

## 🛡️ Exception Handling Strategy

- **Business Exceptions**: Handled based on validation rules
- **System Exceptions**: Handled with retries and logging
- Detailed logs: Info, Warning, Error, Fatal
- Screenshot capture on failures

---

## ⚙️ Configuration Management

- Uses **Orchestrator Assets** for environment-specific values
- Excel-based configuration for ease of updates

### 🔑 Key Config Items
- Word template paths
- Output folders
- Queue and asset names

---

## 🔍 Technical Implementation Details

### 📄 Word Integration
- `WordApplicationScope` for editing templates
- Automated content population and PDF conversion

### 📊 Excel Integration
- `ExcelApplicationScope` for reading data
- Filters hired candidates using DataTable operations

### 📥 Queue Management
- Creates and consumes Orchestrator queue items
- Tracks and updates transaction statuses

---

## ✅ Strengths and 📌 Limitations

### ✅ Strengths
- Clean REFramework implementation
- Robust exception and transaction handling
- Reusable and modular components
- Testing framework included

### ⚠️ Limitations
- Limited parallelism
- Relies on installed Microsoft Office applications
- Configuration could be further centralized

---

## 💡 Recommendations for Improvement

- Implement parallel bots for faster processing
- Email notification on offer letter generation
- Dashboard integration for better insights
- Digital signature integration for PDF outputs
- Version control for templates

---

## 🏁 Conclusion

This automation project successfully reduces manual workload and enhances consistency in HR offer letter generation. Built with best practices and scalability in mind, it serves as a valuable asset in modern HR operations.

---

## 📬 Contact

For feedback, suggestions, or contributions, please feel free to open an issue or submit a pull request.

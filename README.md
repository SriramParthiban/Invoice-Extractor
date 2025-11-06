# 🧾 Invoice Parser Lite – AI-Powered Invoice Data Extractor (n8n Workflow)

## 📌 Overview
**Invoice Parser Lite** is an intelligent automation workflow built with **n8n** that extracts, interprets, and organizes invoice data directly into **Google Sheets**.  
It leverages **Google Drive**, **Gemini AI**, and **Google Sheets API** to automate the process of collecting and parsing invoice details without any manual effort.

This lightweight version focuses on simplicity and reliability while ensuring accurate data capture for finance or operations teams.

---

## ⚙️ Tech Stack
- **n8n** (Low-code workflow automation)
- **Google Drive API** (File retrieval & management)
- **Gemini AI (Google Generative AI)** (Invoice text extraction & understanding)
- **Google Sheets API** (Structured data storage)

---

## 🚀 Workflow Summary
### 🔁 Flow Breakdown
1. **Trigger:**  
   The workflow starts automatically whenever a new invoice is added to a **specific Google Drive folder**.

2. **File Fetch:**  
   n8n retrieves the invoice (PDF or image) using the **Google Drive node**.

3. **AI Processing (Gemini):**  
   The file content is sent to **Gemini AI**, which performs **OCR** and **data extraction** to understand key invoice fields like:
   - Vendor Name  
   - Invoice Number  
   - Date  
   - Amount  
   - Tax  
   - Total Due  

4. **Data Structuring:**  
   The extracted text is formatted into structured JSON for better readability and consistency.

5. **Google Sheets Update:**  
   Each invoice entry is appended as a new row in a **Google Sheet**, creating a centralized and searchable invoice database.

6. **Optional Notifications (Customizable):**  
   You can easily extend this workflow to send notifications via email, Slack, or WhatsApp when new invoices are processed.

---

## 🧩 Workflow Nodes
| Node Name | Function |
|------------|-----------|
| **Google Drive (Trigger)** | Detects and retrieves new invoices. |
| **HTTP Request / Gemini** | Sends invoice data for AI-powered text extraction. |
| **Set / Function Node** | Cleans and structures the extracted fields. |
| **Google Sheets** | Inserts parsed data into your chosen spreadsheet. |

---

## 🧠 AI Prompt Used (Gemini)
The AI is instructed to:
> “Extract only the key invoice details such as vendor name, invoice number, date, subtotal, tax, and total amount. Return data in JSON format.”

This ensures consistent and machine-readable results.

---

## 📊 Example Output (in Google Sheets)
| Vendor | Invoice No | Date | Amount | Tax | Total |
|--------|-------------|------|--------|-----|-------|
| ABC Pvt Ltd | INV-2025-08 | 2025-11-04 | ₹12,000 | ₹720 | ₹12,720 |

---

## 🧱 Folder & Sheet Setup
Before activating the workflow:
1. Create a **Google Drive folder** for invoices.  
2. Create a **Google Sheet** with appropriate columns (Vendor, Invoice No, Date, Amount, Tax, Total).  
3. Connect Google credentials in n8n (OAuth).  
4. Paste your **Gemini API key** in the designated node.

---

## 🧠 Why It’s “Lite”
This version is built for **speed and simplicity**:
- Minimal nodes  
- Fast execution  
- Easily extendable (notifications, database integration, etc.)

---

## 💡 Future Enhancements
- Integrate **email parsing** to auto-fetch invoices from Gmail.  
- Add **error logging** and **duplicate detection**.  
- Store parsed invoices in **Google Cloud Storage** or **Airtable**.  
- Use **OpenAI Vision** or **Claude 3** for multi-language invoice support.

---

## 🧩 Author
👤 **Sriram Parthiban**  
Automation Specialist | AI Workflow Builder  
🔗 *Building smarter workflows with n8n & AI.*

---

## 📜 License
This project is licensed under the MIT License.

---


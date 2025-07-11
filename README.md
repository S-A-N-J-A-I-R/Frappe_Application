# Frappe Assessment App

This custom Frappe app was developed to demonstrate two key features:

1. **Bulk Conversion of Leads to Customers**
2. **Automated Event Reminders**

---

## 📌 Features

### 1. Bulk Convert Leads to Customers

- Adds a **custom submenu** under the **Actions** dropdown in the Lead List View.
- Allows users to **select multiple leads** and convert them into Customers in bulk.
- Creates new Customer records using lead data.
- Automatically updates the lead status to **"Converted"** after conversion.

#### Technical Highlights

- Custom List View button (`lead_list.js`)
- Backend logic written in `api.py`
- Linked using `hooks.py` with the `doctype_js` config
- Uses `frappe.whitelist()` to expose the backend method to JS

---

### 2. Automated Reminders for Events

- Adds a **"Send Reminder"** checkbox to the Event doctype.
- Sends automatic reminders at:
  - 1 Hour before the event
  - 1 Day before the event
  - 1 Week before the event
- Triggers reminders via **email notifications**.

#### Technical Highlights

- Scheduled background jobs in `event_reminders.py`
- Registered in `hooks.py` under `scheduler_events`
- Uses `frappe.sendmail()` to notify Event owners

---

## 🛠️ Installation

1. Get the app:
   ```bash
   bench get-app frappe_assessment [repo-url-if-public]

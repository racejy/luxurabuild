# luxurabuild

LuxuraBuild is a lightweight, local-first web application for generating construction draw sheets quickly and accurately. It eliminates repetitive manual entry by auto-populating subcontractor data (name, address, cost codes) and exporting clean draw sheets to Excel or PDF.

This tool is designed for internal office use, prioritizing speed, simplicity, and reliability.

---

## Key Features

- Auto-populated subcontractor fields (name, address, cost code)
- Simple draw sheet builder with editable line items
- Add and remove rows quickly
- One-click export to Excel and PDF
- Local-only execution (no cloud, no authentication)
- Minimal setup and fast iteration

---

## Tech Stack

- Backend: Python + Flask  
- Database: SQLite (local-only)  
- Frontend: HTML, CSS, minimal JavaScript  
- Exports: Excel (.xlsx) and PDF  

No external services. No third-party accounts. No network dependency.

---

## Project Structure

luxurabuild/
├── app.py # Flask application entry point
├── requirements.txt # Python dependencies
├── README.md
├── LICENSE
├── .gitignore
│
├── data/
│ ├── schema.sql # Database schema (no data committed)
│
├── templates/
│ ├── index.html # Draw sheet builder UI
│
├── static/
│ ├── css/
│ │ └── styles.css
│ └── js/
│ └── app.js
│
├── exports/ # Generated Excel / PDF files (gitignored)

---

## Getting Started

### 1. Clone the Repository

bash
git clone https://github.com/your-username/luxurabuild.git
cd luxurabuild

### 2. Create a Virtual Environment

python3 -m venv venv
source venv/bin/activate

### 3. Install Dependencies

pip install -r requirements.txt

### 4. Initialize the Database

sqlite3 data/luxurabuild.db < data/schema.sql

### 5. Run the App

python app.py

### 6. Open:

http://localhost:5000

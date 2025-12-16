# LuxuraBuild

LuxuraBuild is a lightweight, local-first web application for construction offices to create monthly draw sheets quickly and accurately.

The primary problem it solves is eliminating repetitive manual entry of subcontractor information (name, address, cost code) when preparing draw sheets.

This tool is designed for internal office use only and runs entirely on a local machine. There is no authentication, no cloud storage, and no external dependencies beyond the local runtime.

---

## Core User Workflow

1. Office staff opens the LuxuraBuild web app in a browser.
2. The user starts a new draw sheet.
3. For each line item in the draw:
   - The user selects a subcontractor from a dropdown list.
   - Subcontractor fields (name, address, cost code) are automatically populated.
   - The user manually enters:
     - Description of work
     - Scheduled value
     - Previous draw amount
     - This draw amount
4. The user can add or remove line items freely.
5. The completed draw sheet can be exported as:
   - Excel (.xlsx)
   - PDF (print-ready)

The goal is speed and accuracy, not visual complexity.

---

## Data Model

### Subcontractor
Each subcontractor has the following fields:
- id
- company_name
- address
- cost_code

Subcontractors are stored locally (e.g., JSON or local database) and reused across draw sheets.

### Draw Sheet
A draw sheet contains:
- project_name
- draw_number
- draw_date
- line_items[]

### Line Item
Each line item contains:
- subcontractor_id
- description
- scheduled_value
- previous_draw
- current_draw
- total_completed (calculated)
- balance_remaining (calculated)

---

## Key Requirements

- Auto-populate subcontractor fields when selected
- Editable table-style interface for draw line items
- Add/remove rows instantly
- Calculated fields update automatically
- One-click export to Excel and PDF
- Runs fully offline
- No user accounts, logins, or permissions
- Minimal UI; function over form

---

## Non-Goals

- No cloud sync
- No multi-user collaboration
- No accounting system integration
- No long-term storage beyond local files

---

## Intended Audience

Construction office managers and administrative staff who prepare monthly draw requests and need a faster, less error-prone workflow.

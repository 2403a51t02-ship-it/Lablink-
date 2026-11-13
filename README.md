<<<<<<< HEAD
# LabLink – Full-Stack Laboratory Equipment Booking Portal

This project uses the uploaded LabLink HTML interface with a Node.js/Express backend and shared JSON database. It is intended as a working college project/demo, not a production university identity system.

## Features
- Original LabLink role-based UI: Student, Faculty, Store In-charge and Admin.
- Student and faculty bookings, printable receipts and receipt-code verification.
- Student bookings require faculty coordinator name and official email.
- Each booking reserves one physical unit.
- Date-range and session-time overlap checks run on the server. Pending, Approved and Issued bookings reserve stock; Returned and Rejected bookings release it.
- The server rechecks stock when Store In-charge approves a request. Simultaneous requests are handled in one Node process with synchronous database read/write operations, preventing last-unit overbooking in this single-server setup.
- Admin and Store In-charge can add equipment with a quantity, update quantity/status and remove equipment when it has no active booking.
- Store workflow: verify receipt, approve/reject, issue, record return and condition.
- Late return fine of ₹250, plus an optional damage fine. Borrowers report payment; Store In-charge verifies and clears it.
- Store booking/equipment history and admin overview.
- Shared persistent data in `data/db.json` for users accessing the same running server.

## Requirements
- Node.js 18 or newer
- VS Code (recommended)

## Run on Windows / VS Code
1. Extract the ZIP.
2. Open the `LabLink_FullStack` folder in VS Code.
3. Open Terminal → New Terminal.
4. Run:
   ```bash
   npm install
   npm start
   ```
5. Open `http://localhost:3000` in Chrome.

You can also double-click `start.bat` on Windows.

## Demo login
| Role | Login |
|---|---|
| Student | Select Student and enter an enrollment number (example: `2403CSE001`) |
| Faculty | Select Faculty and enter a name |
| Store In-charge | Username `storeowner`, password `store123` |
| Admin | Username `admin`, password `admin123` |

Student/faculty identity-only login is only for demonstration; it does not verify university identity. Change staff passwords and `JWT_SECRET` before sharing/deployment. Copy `.env.example` to `.env` and set your own values.

## Important notes
- All clients must use the same server address to share bookings and inventory. `localhost` works only on the computer running the server. For other devices on the same Wi-Fi, use the host computer's LAN IP and allow the Node port through Windows Firewall.
- The included JSON database is suitable for a classroom prototype and single Node server. For multi-instance/production deployment, use PostgreSQL/MySQL and database transactions/locking, HTTPS, institutional login, backups and audit logging.
- The portal records payment confirmation; it does not process online payments.
- Do not expose this demo with default passwords on the public internet.

## Project structure
```text
LabLink_FullStack/
├── public/index.html
├── data/db.json
├── server.js
├── package.json
├── .env.example
├── .gitignore
├── start.bat
└── README.md
```

## API routes
- `POST /api/auth/login`
- `GET /api/bootstrap`
- `POST /api/bookings`
- `PATCH /api/bookings/:ref/action`
- `PATCH /api/bookings/:ref/fine-payment`
- `PATCH /api/bookings/:ref/fine-clear`
- `POST /api/equipment`
- `PATCH /api/equipment/:id/quantity`
- `PATCH /api/equipment/:id/status`
- `DELETE /api/equipment/:id`
- `GET /api/health`
=======
# Lablink-
>>>>>>> 7014b7660f9e6fe7f0b441497065ad6f872f0141

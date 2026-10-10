University Research Opportunity Portal
======================================
Stack: Python (Flask) REST API + MySQL + plain HTML/CSS/JavaScript.
No data is hard-coded anywhere: the list starts empty and everything comes from MySQL.

1) Make sure MySQL is running.
2) Set your MySQL login (or edit backend/config.py):
     Windows (PowerShell):  $env:DB_USER="root"; $env:DB_PASSWORD="your_password"
     Mac/Linux:             export DB_USER=root DB_PASSWORD=your_password
3) Install and run:
     cd backend
     pip install -r requirements.txt
     python app.py
4) Open http://localhost:5000

The database and table are created automatically on first run.
(Or run schema.sql manually:  mysql -u root -p < backend/schema.sql)

API
  POST   /api/opportunities        201 Created / 400 Bad Request
  GET    /api/opportunities        200 OK
  GET    /api/opportunities/:id    200 OK / 404 Not Found
  PUT    /api/opportunities/:id    200 OK / 400 / 404   (partial updates allowed)
  DELETE /api/opportunities/:id    200 OK / 404
  Unexpected errors return 500 Internal Server Error (JSON).

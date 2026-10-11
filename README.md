# Research Portal

## Project Overview

The Research Portal is a web-based application developed to manage and display research opportunities. It allows users to view available research projects and access information about faculty members, departments, required skills, available positions, and application deadlines.

The project uses a frontend interface, a Flask backend, and a MySQL database to manage research opportunities.

## Features

- View all research opportunities.
- View a specific research opportunity by ID.
- Add new research opportunities.
- Update existing research opportunities.
- Delete research opportunities.
- Store research information in a MySQL database.
- REST API for managing research opportunities.
- Input validation for research opportunity data.

## Technologies Used

### Frontend
- HTML
- CSS
- JavaScript

### Backend
- Python
- Flask
- REST API

### Database
- MySQL
- PyMySQL

### API Testing
- Postman

### Version Control
- Git
- GitHub

## Project Structure

```text
research_portal/
│
├── backend/
│   ├── app.py
│   ├── db.py
│   ├── config.py
│   └── requirements.txt
│
├── frontend/
│   ├── index.html
│   ├── style.css
│   └── script.js
│
├── .gitignore
└── README.md
```

## Getting Started

### Prerequisites

- Python 3.8 or higher
- MySQL Server
- Git
- Postman (optional, for API testing)

### 1. Clone the Repository

```bash
git clone https://github.com/<your-username>/research_portal.git
cd research_portal
```

### 2. Set Up the Database

Log in to MySQL and create the database and table:

```sql
CREATE DATABASE research_portal;
USE research_portal;

CREATE TABLE research_opportunities (
    id INT AUTO_INCREMENT PRIMARY KEY,
    title VARCHAR(255) NOT NULL,
    faculty_name VARCHAR(150) NOT NULL,
    department VARCHAR(150) NOT NULL,
    required_skills TEXT,
    positions_available INT NOT NULL,
    deadline DATE NOT NULL
);
```

> Adjust the table and column names to match your `app.py` if they differ.

### 3. Configure the Backend

Open `backend/config.py` and set your MySQL credentials:

```python
DB_HOST = "localhost"
DB_USER = "your_username"
DB_PASSWORD = "your_password"
DB_NAME = "research_portal"
```

### 4. Install Dependencies

```bash
cd backend
python -m venv venv
source venv/bin/activate        # On Windows: venv\Scripts\activate
pip install -r requirements.txt
```

### 5. Run the Backend

```bash
python app.py
```

The API will be available at `http://127.0.0.1:5000`.

### 6. Run the Frontend

Open `frontend/index.html` in your browser, or serve it with a simple local server:

```bash
cd frontend
python -m http.server 8000
```

Then visit `http://localhost:8000`.

## API Endpoints

| Method | Endpoint                 | Description                           |
|--------|--------------------------|---------------------------------------|
| GET    | `/research`              | Get all research opportunities        |
| GET    | `/research/<id>`         | Get a research opportunity by ID      |
| POST   | `/research`              | Add a new research opportunity        |
| PUT    | `/research/<id>`         | Update an existing research opportunity |
| DELETE | `/research/<id>`         | Delete a research opportunity         |

> Update the route paths above if your `app.py` uses different ones.

### Example Request Body (POST / PUT)

```json
{
  "title": "Machine Learning for Healthcare",
  "faculty_name": "Dr. Jane Smith",
  "department": "Computer Science",
  "required_skills": "Python, Machine Learning, Data Analysis",
  "positions_available": 2,
  "deadline": "2026-12-31"
}
```



## Testing the API

1. Start the Flask server.
2. Open Postman.
3. Send requests to the endpoints listed above.
4. Verify responses and confirm changes in the MySQL database.

## Future Improvements

- User authentication (student and faculty roles).
- Search and filter by department, skills, or deadline.
- Application submission for students.
- Deployment to a cloud platform.

## License

This project is intended for educational purposes. Add a license of your choice if you plan to distribute it.

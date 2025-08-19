# Hotel Automation (Otel Otomasyonu)

This is a **hotel management automation project** built with **Python, PyQt5, and SQLite** as a 9th-grade school project.  
The application includes user registration, login, reservation management, and profile settings — all backed by a local database.

---

## Features

- **User Registration & Login**  
  - Prevents duplicate accounts using email check  
  - Stores user info in a local SQLite database  

- **Reservation System**  
  - Add reservations with date and guest count  
  - View active reservations  
  - Cancel selected reservations  

- **Profile Management**  
  - Change email or password  
  - Delete account completely  

- **Database Integration**  
  - Data persistence using `sqlite3`  
  - User table automatically created on startup  

- **Clean User Interface**  
  - Built with PyQt5  
  - Screen transitions using QStackedWidget  

---

## Requirements

- **Python 3.6+**  
- **PyQt5**  

Install required libraries:
```bash
pip install PyQt5
```

---

## How to Run

1. Clone or download the project folder:
```bash
git clone https://github.com/Brkberber/hotel-automation.git
cd hotel-automation
```

2. Ensure the following files are in the same directory:  
   - `main.py` (main logic and UI navigation)  
   - `kayit.py`, `giris.py`, `baslangic.py`, `uygulama.py` (UI classes from Qt Designer)  
   - `veritabani.py` (SQLite database functions)  

3. Run the application:
```bash
python main.py
```

The database (`proje.db`) will be automatically created if it doesn’t exist.

---

## Database Design

The database contains a single table: **USERS**  
```sql
CREATE TABLE IF NOT EXISTS USERS (
    id INTEGER PRIMARY KEY,
    name TEXT,
    lastname TEXT,
    email TEXT,
    password TEXT,
    rvm BOOL,
    rezervasyonlar TEXT
);
```

### Main functions in `veritabani.py`:
- `create_table()` → Creates USERS table if not exists  
- `insert(name, lastname, email, password, rvm, rezervasyonlar)` → Adds a new user  
- `search_user(email)` → Fetches user info by email  
- `update_password(email, newPassword)` → Updates password  
- `update_email(email, newEmail)` → Updates email address  
- `delete_account(email)` → Deletes a user account  
- `rezervasyonlar(email, newRezervasyon)` → Updates reservation data  

---

## File Structure

```
hotel-automation/
│
├── main.py            # Main application logic
├── kayit.py           # Registration UI
├── giris.py           # Login UI
├── baslangic.py       # Start screen UI
├── uygulama.py        # Reservation management UI
├── veritabani.py      # SQLite database functions
└── README.md          # Project documentation
```

---

## Future Improvements

- Admin panel to view all users and reservations  
- Add room pricing and availability system  
- Export reservations to PDF/Excel  
- Improve UI styling and add theme support  

---

## License

This project was developed as a **school project** and is free for educational use. You may modify and share it.  

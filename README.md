Odoo Custom Modules
A collection of custom Odoo 18 modules built from scratch to demonstrate real-world Odoo development skills — including model design, relationships, computed fields, business logic, and UI views.

Modules Included

### 1.My Library — `my_library`
A simple library book management module — the starting point of Odoo development.

**Features:**
- Add and manage books with title, author, price, and publish date
- Track availability status of each book

**Technical:**
- Custom model `library.book`
- Fields: `Char`, `Float`, `Date`, `Boolean`
- XML list and form views
- Access control via `ir.model.access.csv`

---

### 2.School Management System — `school_management`
A complete, production-ready school management module covering all core school operations.

**Features:**
- Student enrollment and profile management
- Teacher management with qualifications and salary
- Classroom management with auto student count
- Subject management linked to teachers and classes
- Daily attendance tracking (Present / Absent / Leave)
- Exam creation with auto grade and percentage calculation
- Fee management with paid/unpaid workflow

**Technical:**
- 7 interconnected models
- `Many2one`, `One2many`, `Many2many` relationships
- Computed fields with `@api.depends` — percentage, grade, total students
- `mail.thread` & `mail.activity.mixin` — chatter and activity tracking
- Business logic method — `action_mark_paid()` auto-sets payment date
- `store=True` on computed fields for database-level querying
- Selection field workflows — pass/fail, paid/unpaid, attendance status

---

## Repository Structure
odoo-testing-modules/
├── my_library/
│   ├── __manifest__.py
│   ├── __init__.py
│   ├── models/
│   │   ├── __init__.py
│   │   └── library_book.py
│   ├── views/
│   │   └── library_book_views.xml
│   └── security/
│       └── ir.model.access.csv
│
└── school_management/
    ├── __manifest__.py
    ├── __init__.py
    ├── models/
    │   ├── __init__.py
    │   ├── student.py
    │   ├── teacher.py
    │   ├── classroom.py
    │   ├── subject.py
    │   ├── attendance.py
    │   ├── exam.py
    │   └── fee.py
    ├── views/
    │   └── school_views.xml
    └── security/
        └── ir.model.access.csv

---

## Tech Stack

| Layer | Technology |
|---|---|
| Language | Python 3 |
| Framework | Odoo 18 |
| Database | PostgreSQL (via Odoo ORM) |
| Views | XML (List, Form, Search) |
| Security | ir.model.access.csv |
| Messaging | mail.thread, mail.activity.mixin |

---

## Installation

1. Clone this repository into your Odoo addons directory:
```bash
git clone https://github.com/anumbano/odoo-testing-modules.git
```

2. Add the module path to your `odoo.conf`:
```
addons_path = /path/to/odoo/addons,/path/to/odoo-testing-modules
```

3. Restart Odoo and update the app list:
```bash
./odoo-bin -c odoo.conf -u all
```

4. Go to **Apps**, search for **"My Library"** or **"School Management System"** and install.

---

##Development Progress

| Module | Status | Complexity |
|---|---|---|
| My Library | Complete | Beginner |
| School Management System | Complete | Intermediate |
| More coming soon... | In Progress | — |

---

## Author

**Anum Bano**
- GitHub: [@anumbano](https://github.com/anumbano)
- Email: anum.anwar332@gmail.com
- Karachi, Pakistan

*Fresh CS graduate passionate about Odoo development, Python backend, and building real-world business solutions.*

---

##License
This repository is open source and available for learning and portfolio purposes.

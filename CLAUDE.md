# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Development Commands

### Running the Application
To start the Flask development server:
```bash
python expense-tracker/app.py
```
The application will be available at `http://localhost:5001`.

### Installing Dependencies
To install the required Python packages:
```bash
pip install -r expense-tracker/requirements.txt
```

### Running Tests
The project uses pytest for testing. To run all tests:
```bash
pytest
```
To run tests with verbose output:
```bash
pytest -v
```

### Linting
There is no configured linter in the project. If you wish to add one, consider using flake8 or pylint.

## Project Structure

### High-Level Architecture
This is a Flask web application with the following main components:

- **`app.py`**: The main Flask application containing route definitions and application setup.
- **`templates/`**: Contains HTML templates for the web pages (base.html, landing.html, login.html, register.html).
- **`static/`**: Contains static assets:
  - `css/style.css`: Stylesheet for the application.
  - `js/main.js`: JavaScript file for client-side logic.
- **`database/`**: Contains database-related code:
  - `db.py`: (To be implemented) Will handle database connections, initialization, and seeding.
  - `__init__.py`: Package initializer.

### Data Flow
1. Users interact with the web interface via routes defined in `app.py`.
2. Templates are rendered using Jinja2, with base.html providing a common layout.
3. Static assets (CSS, JS) are served from the `static/` directory.
4. Data persistence is planned to be handled via SQLite through the `database/db.py` module (currently a stub).

### Key Files
- `app.py`: Entry point and route definitions.
- `templates/base.html`: Base template defining the common layout and including CSS/JS.
- `requirements.txt`: Lists Python dependencies (Flask, Werkzeug, pytest, pytest-flask).

## Development Guidelines
- Follow the existing code style in the project.
- When adding new features, consider extending the route handlers in `app.py` and creating corresponding templates.
- For database operations, implement the functions in `database/db.py` as indicated by the comments in the file.
- Keep templates DRY by extending `base.html` for new pages.
- Static assets should be kept minimal; add CSS to `style.css` and JavaScript to `main.js`.

## Notes
- The application is currently in an early stage with many features marked as "coming in Step X".
- The database module is a stub and needs to be implemented according to the comments in `database/db.py`.
- The project uses Flask's built-in development server; for production, consider using a WSGI server like Gunicorn.
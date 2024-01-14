# 1.0 Overview

This repository documents the process of building a Django application, outlining key steps from setting up the environment to configuring essential components.

## 1.1 Installation

To install necessary packages:

```bash
pip install -r requirements.txt
```

## 1.2 Configuration

### Creating .env File

After cloning the repository, create a `.env` file in the `personal_portfolio` directory. Add environment variables like `SECRET_KEY`.

### Database Setup

Since `db.sqlite3` is included in `.gitignore` for security and size considerations, it won't be available in the cloned repository. You'll need to set up the database locally:

```bash
python manage.py migrate
```

This command initializes a new `db.sqlite3` file in your local project directory.

## 1.3 Running the Server

To start the Django development server:

```bash
python manage.py runserver
```

## 1.4 Accessing the Application

- **Project Page**: Navigate to http://localhost:8000/projects.
- **Admin Page**: Accessible at http://localhost:8000/admin.


# 2.0 Project Structure

## 2.1 personal_portfolio/ (Django Project Directory)

**Purpose:** This directory houses the settings and configurations for the entire Django project.

**Contains:**

- `__init__.py`: An empty file that tells Python that this directory should be considered a Python package.
- `asgi.py`: An entry-point for ASGI-compatible web servers to serve the project.
- `settings.py`: Contains settings/configurations for the Django project (like installed apps, database configurations, etc.).
- `urls.py`: The URL declarations for the Django project; a “table of contents” for the web application.
- `wsgi.py`: An entry-point for WSGI-compatible web servers to serve the project.

## 2.2 pages/ (Django App Directory)

**Purpose:** A Django app dedicated to handling the static pages of the portfolio, like the home or about page.

**Contains:**

- `admin.py`, `apps.py`, `models.py`, `tests.py`, `views.py`: Standard Django app files for admin configurations, app configurations, database models, tests, and view logic, respectively.
- `urls.py` (manually added): URL patterns specific to the pages app.
- `migrations/`: Stores migration files for database changes related to the pages app.
- `templates/pages/`: Template directory specific to the pages app, storing HTML files like `home.html` for rendering views.

## 2.3 projects/ (Django App Directory)

**Purpose:** A Django app for showcasing portfolio projects. It handles dynamic content related to the projects.

**Contains:**

- Similar to `pages/`, it has `admin.py`, `apps.py`, `models.py`, `tests.py`, `views.py`.
- `urls.py` (manually added): URL patterns specific to the projects app.
- `migrations/`: Stores migration files for database changes related to the projects app.
- `templates/projects/`: Contains templates like `project_index.html` and `project_detail.html` for rendering project information.


## 2.4 templates/ (Global Templates Directory)

**Purpose:** Contains global templates that can be used across different apps within the project.

**Contains:**

- `base.html`: A base template file that includes common HTML structure and Bootstrap styling, which can be extended by other templates.

## 2.5 uploads/ (Media Storage Directory)

**Purpose:** Stores uploaded media files like images for the projects.

**Configured in:** `settings.py` with the `MEDIA_ROOT` setting.

## Other Key Files

- `manage.py`: Django’s command-line utility for administrative tasks.
- `db.sqlite3`: The SQLite database file for the project.
- `requirements.txt`: Lists all Python dependencies required for the project, ensuring consistent environments across setups. This file is used in conjunction with conda env or other virtual environment managers to install the necessary packages.

For detailed guidance, refer to the [Real Python Django Tutorial](https://realpython.com/get-started-with-django-1/).

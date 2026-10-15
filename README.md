# Recruitment Platform

A recruitment platform developed with **Django**: recruiters can publish job listings, candidates can apply with their CVs and cover letters, and an integrated messaging system enables communication between both parties.

## Features

**User Accounts**
- Two distinct profile types: **Candidate** and **Recruiter** (a user cannot have both roles simultaneously).
- Separate registration and login processes for each role.
- Candidate profile: skills, work experience, education, and profile picture.
- Recruiter profile: company name, company description, and logo.

**Job Listings**
- Recruiters can publish job openings with details such as contract type, location, salary, and application deadline.
- Active job listings, with automatic exclusion of positions a logged-in candidate has already applied for.

**Applications**
- Apply for a job by uploading a CV and cover letter.
- Application status tracking: pending, under review, interview, accepted, or rejected.
- Candidates can apply only once per job listing.

**Messaging**
- Direct messaging between candidates and recruiters, linked or unlinked to a specific application.
- Conversation threads with replies and read/unread status tracking.

**Dashboard**
- Dedicated application (`apps/dashboard`), currently in its initial development stage.

## Tech Stack

- **Django 5.2**
- **SQLite** (development database)
- **django-crispy-forms** + **crispy-bootstrap5** — form rendering and styling.
- **django-debug-toolbar** — development debugging.
- Internationalization enabled (`locale/fr`).

## Prerequisites

- Python 3.13
- pip

## Installation and Setup

```bash
git clone https://github.com/AlahyaneYassine/recruitment_platform.git
cd recruitment_platform

python -m venv venv
source venv/bin/activate  # Or venv\Scripts\activate on Windows

pip install -r requirements.txt
pip install django-debug-toolbar  # Dependency used but missing from requirements.txt

python manage.py migrate
python manage.py createsuperuser
python manage.py runserver
```

Then open `http://127.0.0.1:8000` in your browser.

## Project Structure

```text
recruitment_platform/
├── cand/                  # Django project configuration (settings, URLs, WSGI/ASGI)
├── apps/
│   ├── accounts/          # Users and candidate/recruiter profiles
│   ├── jobs/              # Job listings
│   ├── applications/      # Applications (CV, cover letter, status)
│   ├── messaging/         # Candidate ↔ recruiter messaging
│   └── dashboard/        # Dashboard (under development)
├── templates/             # Global templates
├── media/                 # Uploaded files (CVs, photos, etc.) — not version-controlled
└── requirements.txt
```

## Author

**Yassine Alahyane**

Cybersecurity Engineering Student

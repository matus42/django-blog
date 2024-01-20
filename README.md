# About App Implementation Plan

This document outlines the user stories, acceptance criteria, model design, and implementation steps for the About app in our Django project.

## User Stories and Acceptance Criteria

### For Site Users

- **User Story:** As a Site User, I want to click the About link to read about the site so that I can learn more about its background and purpose.

- **Acceptance Criteria:**
  - The navigation menu includes an About link.
  - Clicking the About link navigates to the About Me page.
  - The About Me page displays a title, the main content, and the last updated timestamp.

### For Site Admins

- **User Story:** As a Site Admin, I want to create or update the About information so that I can share or modify the site's background and purpose with users.

- **Acceptance Criteria:**
  - There is access to a form in the admin panel to create or update the About Me content.
  - The form allows for editing the title and content.
  - The system automatically updates the last modified timestamp upon saving.
  - Any changes made in the admin panel are immediately reflected on the About page.

## Model Design

The model for the About app will be simple and will be named `About`. It includes the following fields:

- `title` (CharField): A field for the page title.
- `content` (TextField): A field for the main About Me content.
- `updated_on` (DateTimeField): A field to auto-update with the current timestamp upon saving changes.

## Entity-Relationship Diagram (ERD)

The ERD for the About model consists of:

- `About`
  - `title`: CharField
  - `content`: TextField
  - `updated_on`: DateTimeField, auto_now_add=True

## Implementation Steps

### Creating the App

Execute the following command to create the About app:

`bash`
python manage.py startapp about


## Files to Update or Create

- `models.py`: Define the `About` model with `title`, `content`, and `updated_on` fields.
- `admin.py`: Register the `About` model to enable admin management.
- `views.py`: Create a view to render the About page.
- `urls.py` (in the `about` app directory): Set up the URL pattern for the About page.
- `templates/about/about.html`: Create the template for the About page.

## Project-Level Changes

- Add `about` to the `INSTALLED_APPS` list in `settings.py`.
- Import and include the `about` app's `urls.py` in the project-level `urls.py` file.

## Base Template Update

- Add an About link to the `base.html` template for site-wide navigation to the About Me page.

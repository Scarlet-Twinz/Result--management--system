# JPTS University Result Management System

A browser-based academic result-management interface built for a university-focused workflow. The repository contains a large static frontend with role-specific dashboards, Firebase integration, academic management screens, and a second nested copy of the JPTS grade-system interface.

## Overview

The project presents an academic administration workflow covering student, lecturer, HOD, exam-officer, and administrator views. The current implementation uses HTML, CSS, JavaScript, Bootstrap, Font Awesome, Google Fonts, and Firebase client SDKs.

This repository should be treated as a **frontend/prototype application**, not as a production university information system. Firebase configuration is present in the repository, but production security depends on Firebase Authentication configuration and Firestore/Storage security rules outside the static frontend code.

## Included Interfaces

- Landing page
- Login and registration flow
- Student dashboard
- Lecturer dashboard
- Head of Department dashboard
- Exam Officer dashboard
- Admin dashboard
- Course management
- Student management
- Result management
- Analytics views
- Transcript-related interface

## Data & Authentication

The project includes Firebase client integration for:

- Firebase Authentication
- Cloud Firestore
- Firebase Storage
- Offline Firestore persistence

The browser-facing Firebase configuration is stored in `firebase-config.js`. Firebase web API keys are identifiers rather than server-side secrets, but the associated Firebase project must use restrictive Authentication, Firestore, and Storage security rules before any real student data is handled.

The application also stores some client-side session/profile values in `localStorage`. These values should not be treated as a security boundary.

## Tech Stack

- HTML5
- CSS3
- JavaScript
- Bootstrap 5
- Font Awesome
- Google Fonts
- Firebase Authentication
- Cloud Firestore
- Firebase Storage

## Project Structure

```text
Result--management--system/
├── index.html
├── login.html
├── dashboard.html
├── student-dashboard.html
├── lecturer-dashboard.html
├── hod-dashboard.html
├── exam-officer-dashboard.html
├── admin-dashboard.html
├── auth.js
├── admin.js
├── dashboard.js
├── student-mgt.js
├── result-mgt.js
├── course-mgt.js
├── analytics.js
├── firebase-config.js
├── css/
│   └── style.css
├── assets/
└── jpts-grade system/
    └── ...
```

The nested `jpts-grade system` directory contains another copy of related academic-management assets. It is retained as part of the repository's current structure rather than being presented as a separate production service.

## Running Locally

No Node.js build step is required for the current static frontend.

1. Clone the repository.
2. Open the project folder.
3. Configure the Firebase project used by `firebase-config.js` if you intend to use the Firebase-backed flows.
4. Serve the repository with a local static HTTP server.
5. Open `index.html` and navigate through the available interfaces.

For example:

```bash
python -m http.server 8000
```

Then open:

```text
http://localhost:8000
```

## Security Considerations

This is a portfolio/prototype project. Before production use:

- Enforce least-privilege Firestore security rules.
- Restrict Firebase Storage access by authenticated user and role.
- Do not rely on `localStorage` values for authorization.
- Prevent self-service creation of privileged roles such as administrator unless controlled by trusted server-side logic.
- Validate role and ownership permissions with Firebase security rules, not only frontend JavaScript.
- Configure Firebase Authentication providers and password policies appropriately.
- Remove test data and demo accounts from production projects.

## Project Status

**Status: Functional frontend/prototype with Firebase integration.**

The repository demonstrates a substantial academic-management UI and client-side Firebase workflow, but it is not documented as a production-ready university records platform.

## Author

**Anthony Emmanuella Mmasinachi**  
Full-stack developer focused on frontend engineering, backend systems, APIs, automation, databases, and practical software architecture.

**GitHub Repository:** https://github.com/Scarlet-Twinz/Result--management--system

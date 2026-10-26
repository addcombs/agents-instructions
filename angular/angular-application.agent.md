---
name: angular-application
description: Creates and maintains the Angular frontend in the sibling aws-sandbox-ui project, including its Angular Material layout and light/dark theme toggle.
---

You are an implementation agent for the Angular frontend associated with the `aws-sandbox-api` repository.

## Scope

- The Spring Boot backend lives in `aws-sandbox-api`; the Angular application lives in its sibling directory, `aws-sandbox-ui`, at the workspace root. Resolve the UI path from the parent of this repository and work there. Do not create a nested `frontend` directory inside `aws-sandbox-api`.
- Inspect both the API repository and `aws-sandbox-ui` before making changes. Extend the existing Angular application rather than creating a competing one. If the sibling UI directory does not exist, scaffold the application there using the Angular CLI and the package manager already used by the UI project, if any.
- Keep backend work out of scope unless the user explicitly asks to change it. Do not invent API endpoints or contracts; integrate only against existing documented backend behavior.
- Use standalone Angular components and the conventions of the installed Angular version. Keep dependencies compatible; do not assume that the newest Angular or Angular Material release is appropriate.

## Required application shell

- Add Angular Material and use Material components for the main toolbar and navigation drawer/sidenav.
- Build a responsive shell with a top toolbar and a sidenav containing the application's primary navigation. Show a hamburger button in the toolbar at every viewport size and have it toggle the sidenav open or closed; do not make the desktop sidenav permanently open. Use side mode on wider screens and a dismissible overlay on narrow screens, with accessible expanded state and labels.
- Make the entire shell fill the viewport: give `html` and `body` a definite full height and ensure the root component and sidenav container inherit that height. A `min-height` on `body` alone is not enough when descendants use percentage heights.
- Put an accessible light/dark theme toggle at the top-right of the toolbar. Use a Material icon button with an appropriate icon, tooltip, and accessible label that reflects the action or current theme.
- Apply the selected theme consistently to the toolbar, sidenav, content, text, and surfaces. Initialize from the saved user preference when present; otherwise respect the operating system's color-scheme preference. Persist user changes and update the document theme without a page reload.
- Keep theme state in one reusable, typed service or equivalent shared state mechanism. Avoid scattered direct DOM mutations and duplicated theme logic.

## Implementation and verification

- Follow Angular Material's theming approach for the installed version and ensure all interactive controls are keyboard accessible.
- Keep components focused, styles maintainable, and TypeScript strict. Do not invent API endpoints or application features; use existing backend contracts when integrating data.
- Add or update focused tests for the shell and theme toggle where the project has a test setup.
- Run the frontend's available build and relevant tests. Report the commands run and any failures or unavailable tooling; do not claim validation that was not performed.

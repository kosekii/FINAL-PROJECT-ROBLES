# UniSchedule


**Created by:** Robyn Desiree Gonzales & John Matthew Robles  
*Course Final Project — Week 2 Milestone (September 27, 2026)*  
**Repository:** [https://github.com/robyndgonzales/final-project-robyndgonzales](https://github.com/robyndgonzales/final-project-robyndgonzales)

---

## 1. Overview

UniSchedule is a lightweight student planner built with Flutter for mobile and web. It helps college students manage daily class schedules, track homework deadlines, and prepare for upcoming exams in one clean interface. We designed this app for students who are tired of switching between messy school portals, group chats, and paper notes just to see what is due next.

---

## 2. Setup and Installation

### Built with
- **Flutter SDK:** Version 3.19.x (or newer)
- **Dart SDK:** Version 3.3.x (bundled with Flutter)
- **Primary Test Environment:** Google Chrome Desktop (via DevicePreview)

### Installation Steps

1. **Clone the repository:**
   ```bash
   git clone https://github.com/robyndgonzales/final-project-robyndgonzales.git
   cd final-project-robyndgonzales
   ```

2. **Install project dependencies:**
   ```bash
   flutter pub get
   ```

3. **Configuration:**
   The app runs entirely on local mock data for testing. You do not need any database credentials, third-party accounts, or API keys to run it. If future versions connect to a live backend, environment variables will use placeholders:
   ```text
   API_BASE_URL=https://example.invalid/api
   ```

---

## 3. How to Run It

To launch the project on your computer using Google Chrome, run:

```bash
flutter run -d chrome
```

### What you should see
A Chrome browser window will open displaying our app inside a simulated phone frame (powered by `device_preview`). The app loads directly into the **Home** dashboard, displaying our navy and gold color scheme, today's schedule highlight, and a working bottom navigation bar.

---

## 4. Features and Usage

### Primary Flow

```text
Dashboard (Home) ──> View daily metrics & immediate next class
       │
       ├──> Tasks (Assignments) ──> Review homework & toggle checkboxes
       │
       └──> Schedule / Exams / Profile ──> View upcoming module placeholders
```

### Screen-by-Screen Walkthrough

1. **Dashboard (Home Tab):**
   - Displays a student greeting and today's date badge.
   - Shows three summary metric boxes: classes count, pending tasks, and exams count.
   - Highlights your next class ("Mobile Application Development" in Room 204) with an "Ongoing" status pill.
   - Gives a quick preview of urgent deadlines.

2. **Assignments Screen (Tasks Tab):**
   - Displays a dynamic list of real course tasks loaded from `sample_data.dart`.
   - Each card shows the task title, course name, and due date tag.
   - **Interactive Checkbox:** Tapping any checkbox immediately toggles the item's completion state, changes the tag to "Done", and crosses out the task text.

3. **Navigation Bar (`IndexedStack`):**
   - Clicking between the Home and Tasks tabs keeps your progress alive. If you check off an assignment and switch to Home, the box stays checked when you return.

4. **Schedule, Exams, and Profile Tabs:**
   - Currently display clean placeholder views indicating that timetable filters, exam countdowns, and profile settings are under development for the final sprint.

---

## 5. Project Structure

Here is a map of our modular `lib/` directory for Week 2:

```text
lib/
├── data/
│   └── sample_data.dart          # Local mock list of assignments for testing
├── models/
│   └── assignment.dart           # Blueprint class for task items
├── screens/
│   ├── dashboard_screen.dart     # Overview metrics and next-class card
│   └── assignments_screen.dart   # Scrollable checklist using ListView.builder
├── widgets/
│   └── assignment_card.dart      # Stateful task card with custom checkbox logic
└── main.dart                     # Entry point, theme data, and IndexedStack navigation
```

- **`lib/main.dart`:** Preserves all original starter template comments and manages bottom navigation using an `IndexedStack`.
- **`lib/screens/dashboard_screen.dart`:** Separates the visual dashboard layout from `main.dart` to keep files short and maintainable.
- **`lib/widgets/assignment_card.dart`:** Reusable UI component with local state for crossing off finished assignments.

---

## 6. Screenshots

*Actual screenshots from our running web build inside DevicePreview:*

| 1. Dashboard (Home) | 2. Tasks (Interactive Checkboxes) | 3. Schedule (Placeholder) |
| :---: | :---: | :---: |
| ![Dashboard](docs/screenshots/dashboard.png) | ![Assignments](docs/screenshots/assignments.png) | ![Schedule](docs/screenshots/schedule.png) |

*(Images are stored in `docs/screenshots/`)*

---

## 7. Known Issues and Next Steps

### Known Issues
- **No permanent storage yet:** Checked tasks stay checked while navigating tabs, but refreshing the browser window resets data back to the default `sample_data.dart` state.
- **Static task creation:** The "Add Task" button is currently a UI visual and does not open a bottom sheet modal yet.
- **Remaining tabs:** Timetable filtering by day (Monday–Friday) and the exam countdown view are still placeholder screens.

### Next Steps (Final Sprint)
1. Add `shared_preferences` local persistence so user actions survive page refreshes.
2. Build an "Add Assignment" modal bottom sheet with simple input validation.
3. Build the full Class Schedule timetable view.
4. Run `flutter analyze` and fix any remaining linter hints before the final release.

---

## Security Review

We completed our Week 2 security audit before pushing this repository live. The full checklist is documented in [`SECURITY-CHECKLIST.md`](SECURITY-CHECKLIST.md). No passwords, student records, or API keys are committed to Git history.

---

## AI Usage

This project was developed with assistance from generative AI tools (ChatGPT and Claude) for layout troubleshooting, state preservation research, and boilerplate generation. A comprehensive record of prompts, mistakes caught, and member contributions is available in [`AI-USAGE.md`](AI-USAGE.md).
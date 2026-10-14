# Contributing to CampusMart

Thank you for your interest in contributing to CampusMart! This document describes the values, processes, and rules our team has agreed to follow. Please read it fully before opening an issue or pull request.

## About the Project

CampusMart is a web app where university students can advertise and find services offered by other students, such as graduation photography, course specific tutoring, repairs, and clothes tailoring. Instead of relying on flyers or scattered social media posts, students can list and browse services in one place.

Users sign in with a `.edu` email address. Service providers create listings with descriptions, prices, and images of their work. Clients can search services by keyword and leave reviews and comments. The app is built for NYU students first, with the goal of expanding to other schools later.

## Team Members

| Name        | GitHub                                              |
| ----------- | --------------------------------------------------- |
| Rui Dong    | [RuiDong1](https://github.com/RuiDong1)             |
| Jean Park   | [JunJunHue](https://github.com/JunJunHue)           |
| James Huang | [JamesHuang2004](https://github.com/JamesHuang2004) |
| Colin Sung  | [js10839](https://github.com/js10839)               |
| Jack Jiang  | [Jack-K-Jian] (https://github.com/jack-k-jiang)     |

## Team Norms

### Team Values

- **We work in the open.** All project communication happens in our team's shared channel in the course messaging app, where the instructor and course assistants can see it. We do not use private channels for project decisions.
- **Everyone is a developer.** The Scrum Master and Product Owner roles rotate every sprint so that each member fills each role at least once, and both roles still do design and code work.
- **Asking for help.** If you are stuck on a task for more than an hour or two, post in the team channel describing what you tried and what is blocking you. Blockers are also raised at every standup. Asking for help early is expected, not a weakness.
- **Response time.** Team members respond to messages directed at them within 24 hours. Messages about blockers or pull request reviews should be answered as soon as reasonably possible.
- **Resolving disagreements.** Disagreements are discussed openly in the team channel or at a standup, and each person explains their reasoning. If we cannot reach consensus, the team decides by majority vote. For questions about product direction or feature priority, the Product Owner of the current sprint makes the final call.
- **When a member is not delivering.** A teammate first reaches out directly to check in and offer help. If the issue continues, it is raised at the next standup. If there is still no progress, the Scrum Master reports it to the instructor. We do not cover for members who do not participate.

### Sprint Cadence

Each sprint lasts **2 weeks**. Every sprint begins with a Sprint Planning session, where we choose User Stories from the Product Backlog and break them into Tasks and Spikes, and ends with a Sprint Review and Retrospective.

| Sprint   | Focus                                                                    |
| -------- | ------------------------------------------------------------------------ |
| Sprint 0 | App map, wireframes, clickable prototype, project setup, sprint planning |
| Sprint 1 | Front end built with React                                               |
| Sprint 2 | Back end built with Express.js, with unit tests                          |
| Sprint 3 | Database integration with MongoDB Atlas and mongoose                     |
| Sprint 4 | Deployment                                                               |

### Daily Standups

- Standups are held **three times a week, Monday, Wednesday, and Friday at 1:00 PM**, and last about **15 minutes**.
- All members are expected to attend synchronously, either in person or on video with camera on.
- Each member answers three questions: What did I do since the last standup? What will I do before the next one? Is anything blocking me?
- Members will not cover for other members who do not participate.
- A member who makes no progress on a task for two or more standups in a row will be reported to the instructor.
- Every member pushes their work to GitHub at least once between standups.

### Coding Standards

- **Editor and formatting.** All members use **Visual Studio Code** with the **ESLint** and **Prettier** extensions, and format code on save so formatting stays consistent across the team.
- **Do not over-engineer.** Write the minimum code needed to get a feature working end to end, then iterate to improve it.
- **Always push working code.** If you break the build or tests, fixing them is your top priority.
- **Small, focused commits.** Make granular commits, one per feature or bug fix, with clear single-line messages that describe what changed.
- **Self-documenting code.** Use descriptive variable and function names, and avoid unnecessary abbreviations.
- **No dead code.** Do not leave commented-out or unused code behind. If you see some, delete it.
- **Never commit secrets.** Credentials, API keys, and database connection strings go in a `.env` file, which is already listed in `.gitignore`.
- **Test critical code.** Write automated tests for critical functionality and integration points. Back-end code is tested with mocha and chai, and coverage is checked with c8.
- All code must be peer reviewed and pass tests before it is merged into `master`.

## Git Workflow

We follow the [feature branch workflow](https://knowledge.kitchen/content/courses/agile-development-and-devops/slides/feature-branch-workflow/). The `master` branch must always be in a working, deployable state, and no one commits directly to it.

All work happens in the single shared team repository, [RuiDong1/CampusMart](https://github.com/RuiDong1/CampusMart). Do not fork it.

### Steps

1. **Start from an up-to-date `master`.**
   ```bash
   git checkout master
   git pull origin master
   ```
2. **Create a branch for your issue.** Name it after the type of work and the issue number:
   - `feature/<issue-number>-short-description`, for example `feature/12-listing-page`
   - `fix/<issue-number>-short-description`
   - `spike/<issue-number>-short-description`
   ```bash
   git checkout -b feature/12-listing-page
   ```
3. **Commit small and often** with clear single-line messages.
4. **Push your branch** to GitHub regularly, at least once between standups.
   ```bash
   git push -u origin feature/12-listing-page
   ```
5. **Open a pull request** into `master`. In the description, link the issue (for example `Closes #12`) and briefly explain what changed and how to test it.
6. **Get a review.** At least **one teammate other than the author** must review and approve the pull request before it is merged. Reviewers check that the code works, follows our coding standards, and passes tests.
7. **Merge and clean up.** After approval, merge the pull request and delete the branch.

### Important: Check the Base Repository

Our repository is a fork of the instructor's repository, so GitHub sets the **base repository** of new pull requests to the instructor's repo by default. When opening a pull request, always change the base repository to `RuiDong1/CampusMart` and the base branch to `master`. Otherwise the pull request goes to the instructor and teammates cannot review or merge it.

### Keeping Your Branch Up to Date

If `master` changes while you are working, bring those changes into your branch and resolve any conflicts locally before requesting a review:

```bash
git checkout master
git pull origin master
git checkout feature/12-listing-page
git merge master
```

## Rules of Contributing

### Issues and Labels

- All work must be tied to an Issue in GitHub's Issue tracker. Use the templates in `.github/ISSUE_TEMPLATE/` for user stories, tasks, and spikes.
- Every issue must have one type label: `user story`, `task`, or `spike`.
- Every issue in the current sprint must also have the matching `Sprint N` label. An issue that carries over into the next sprint gets that sprint's label too.
- Every Task must reference the User Story it belongs to, for example `Related to User Story #22`.
- Tasks should be small enough for one person to finish between one standup and the next.

### Task Board

- Each sprint has its own Task Board under the repository's **Projects** tab.
- Assign yourself to an issue before starting it, and move its card across the board as you work so the board always reflects the real status.

### What and How to Contribute

- Pick up tasks from the current sprint's backlog, or ask in the team channel if you are unsure what to work on next.
- Bugs and new ideas should be opened as Issues first and discussed before any code is written.
- Review teammates' pull requests promptly. Reviewing is part of contributing.

### Things to Keep in Mind

- **Use matching git and GitHub usernames.** Contributions are tracked by username, so your local `git config user.name` must match your GitHub username exactly.
- **Do not modify instructor automation files.** The `.automations/`, `.github/hooks/`, `.github/workflows/`, `.cursor/`, and `.claude/` directories are used by the instructor and must not be changed.
- **Do not commit sensitive information** such as passwords, API keys, or users' personal data.
- **Do not add packages that the project rules forbid.** The front end must use React only, without other state managers (such as Redux) or UI frameworks (such as Material UI or Bootstrap).

## Setting Up the Local Development Environment

### Prerequisites

- [Git](https://git-scm.com/)
- [Node.js](https://nodejs.org/) (current LTS version) and npm
- [Visual Studio Code](https://code.visualstudio.com/) with the ESLint and Prettier extensions

### Setup Steps

1. **Clone the repository.**
   ```bash
   git clone https://github.com/RuiDong1/CampusMart.git
   cd CampusMart
   ```
2. **Set your git username** to match your GitHub username.
   ```bash
   git config --global user.name "your-github-username"
   ```
3. **Enable the commit message hook**, which rejects multi-line commit messages.
   ```bash
   chmod a+x .githooks/commit-msg
   git config core.hooksPath ".githooks"
   ```
4. **Install dependencies** once the front end and back end exist.
   ```bash
   cd front-end && npm install
   cd ../back-end && npm install
   ```
5. **Set up environment variables.** Secrets such as the MongoDB Atlas connection string are stored in `.env` files that are never committed. Ask a teammate for the values privately.

## Building and Testing

> This section will be updated as the project reaches each stage.

- **Front end** (Sprint 1): instructions for running the React development server will be added here.
- **Back end** (Sprint 2): instructions for starting the Express.js server and running the mocha and chai unit tests, including the c8 coverage report, will be added here.
- **Database** (Sprint 3): instructions for connecting to MongoDB Atlas will be added here.
- **Deployment** (Sprint 4): deployment instructions will be added here.

All tests must pass before a pull request is merged.

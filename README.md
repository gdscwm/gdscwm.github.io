# gdscwm.github.io

Welcome to the GitHub repository for the Google Developer Student Clubs (GDSC) website at William & Mary!

This project is a collaborative effort to build and maintain our club website. This README explains how to set up the project, work on features, collaborate with teammates, and deploy changes.

## Table of Contents

- [Project Overview](#project-overview)
- [Tech Stack](#tech-stack)
- [Getting Started](#getting-started)
- [Running the Website Locally](#running-the-website-locally)
- [Project Structure](#project-structure)
- [Team Workflow](#team-workflow)
- [Working on a Feature](#working-on-a-feature)
- [Submitting a Pull Request](#submitting-a-pull-request)
- [Code Review and Merging](#code-review-and-merging)
- [Deployment](#deployment)
- [Troubleshooting](#troubleshooting)
- [Team Guidelines](#team-guidelines)

---

## Project Overview

The goal of this project is to create a welcoming, informative, and accessible website for GDSC at William & Mary.

The website will help students learn about the club, discover events and activities, and connect with other students interested in technology, programming, and development.

All team members are encouraged to contribute ideas, develop features, review code, and collaborate on improving the website.

## Tech Stack

The project currently uses:

- **HTML** — Website structure and content.
- **Tailwind CSS v4** — Styling and responsive layouts.
- **Node.js and npm** — Managing development dependencies.
- **Git and GitHub** — Version control and collaboration.
- **GitHub Actions and GitHub Pages** — Automated deployment and website hosting.

## Getting Started

### Prerequisites

Before working on the project, install the following:

1. **Git:** https://git-scm.com/downloads
2. **Node.js and npm:** https://nodejs.org/
3. **Visual Studio Code:** https://code.visualstudio.com/
4. **A GitHub account** with Write access to this repository.

After installation, verify that Git, Node.js, and npm are available in your terminal:

```bash
git --version
node --version
npm --version
```

### 1. Get Repository Access

Ask the project lead or repository administrator to invite your GitHub account to the repository.

You must accept the invitation and have permission to contribute before you can push branches to GitHub.

### 2. Clone the Repository

If you have not downloaded the project before, open a terminal and run:

```bash
git clone https://github.com/gdscwm/gdscwm.github.io.git
cd gdscwm.github.io
```

This downloads the repository to your computer and enters the project directory.

If you already have the repository cloned, open that existing folder in VS Code instead.

### 3. Install Dependencies

From the project directory, run:

```bash
npm ci
```

This installs the dependencies listed in `package-lock.json`.

If `npm ci` fails because the lockfile is missing or out of sync with `package.json`, ask the project lead before changing dependency files.

### 4. Open the Project in VS Code

Open the project folder in VS Code.

You can also run the following command from the project directory if the `code` command is installed:

```bash
code .
```

Open a terminal through **Terminal → New Terminal**.

Make sure your terminal is in the project directory before running Git or npm commands.

## Running the Website Locally

The website uses Tailwind CSS to generate the stylesheet used by the HTML page.

### 1. Start Tailwind CSS

Run:

```bash
npx @tailwindcss/cli -i ./src/input.css -o ./src/output.css --watch
```

This watches the project's CSS entry point and regenerates `src/output.css` when you make changes.

Keep this terminal running while you work.

### 2. Preview the Website

Open `index.html` in your browser.

You can use the **Live Server** extension in VS Code:

1. Install Live Server from the VS Code Extensions panel.
2. Open `index.html`.
3. Right-click the file and select **Open with Live Server**.

Keep both Tailwind's watch process and Live Server running while developing.

When you change your HTML or Tailwind classes, the page should update in the browser. If a new style does not appear, check that Tailwind is still running and refresh the page.

## Project Structure

The project currently follows this general structure:

```text
gdscwm.github.io/
├── .github/
│   └── workflows/
│       └── deploy.yml
├── .gitignore
├── index.html
├── package.json
├── package-lock.json
└── src/
    ├── input.css
    └── output.css
```

### Important Files

- `index.html` — Main HTML page for the website.
- `src/input.css` — Tailwind CSS entry point.
- `src/output.css` — Generated stylesheet linked from the HTML page.
- `package.json` — Project metadata and development dependencies.
- `package-lock.json` — Records the dependency versions used by npm.
- `.gitignore` — Specifies files and folders Git should not track.
- `.github/workflows/deploy.yml` — GitHub Actions workflow for deploying the website.

**Important:** `src/output.css` is generated from `src/input.css` and the HTML files. Do not manually edit the generated stylesheet. Make styling changes in the source files instead.

## Team Workflow

We use Git branches and pull requests to keep collaboration organized and protect the live website.

### Main Branch

The `main` branch is the primary branch of the project.

It should contain the reviewed, approved version of the website. Changes merged into `main` can trigger an automatic deployment to GitHub Pages.

**Do not push feature work directly to `main`.**

### Feature Branches

Each task should have its own branch.

Examples:

- `feature/navbar`
- `feature/homepage-layout`
- `feature/events-section`
- `fix/mobile-navigation`
- `docs/update-readme`

Branch names should be short, descriptive, and related to the task.

### GitHub Issues

Use GitHub Issues to track work.

Each issue should describe a task, its requirements, and how the team will determine when it is complete.

Whenever possible, assign each issue to one teammate so responsibility is clear.

Before beginning a task, check the issue description and ask questions if anything is unclear.

## Working on a Feature

Follow these steps whenever you begin a new task.

### 1. Update Your Local Main Branch

Before creating a new branch, make sure you have the latest version of the project:

```bash
git switch main
git pull origin main
```

This helps prevent you from starting work using an outdated version of the website.

### 2. Create a Feature Branch

Create a branch related to your assigned issue.

For example, if you are building the navigation bar:

```bash
git switch -c feature/navbar
```

This creates the branch and switches you to it.

You can confirm your current branch by running:

```bash
git branch
```

The branch marked with an asterisk (`*`) is your current branch.

### 3. Make Your Changes

Work on your assigned feature in VS Code.

Save your files and preview the changes locally before submitting them.

Keep your work focused on the issue you were assigned. If you discover another feature that needs attention, create a separate issue or discuss it with the project lead.

### 4. Check Your Changes

Before committing, run:

```bash
git status
git diff
```

These commands help you identify which files have changed and review your modifications.

Test the feature in your browser and check that it works at different screen sizes when relevant.

### 5. Commit Your Changes

Stage the files you want to include:

```bash
git add .
```

Create a commit with a descriptive message:

```bash
git commit -m "Add navigation bar"
```

Commit messages should briefly explain what changed.

Examples:

```text
Add responsive navigation bar
Create events section layout
Fix mobile navigation spacing
Update homepage typography
```

### 6. Push Your Branch to GitHub

Push the branch to the remote repository:

```bash
git push -u origin feature/navbar
```

Replace `feature/navbar` with your actual branch name.

The `-u` option sets the upstream branch, making future pushes from that branch simpler. After the first push, you can generally use:

```bash
git push
```

Your feature branch will now be available on GitHub.

**Remember:** Push your feature branch, not `main`.

## Submitting a Pull Request

A pull request (PR) asks the team to review your changes and merge them into another branch.

After pushing your feature branch:

1. Open the repository on GitHub.
2. Navigate to the **Pull requests** tab.
3. Click **New pull request**. You may also see a prompt to create a pull request for your recently pushed branch.
4. Select `main` as the **base** branch.
5. Select your feature branch as the **compare** branch.
6. Review the list of changed files.
7. Click **Create pull request**.

### Pull Request Description

Include a clear description of your changes.

For example:

**Title:** Add responsive navigation bar

**Description:**

- Created the initial navigation bar for the GDSC website.
- Added navigation links to the planned website sections.
- Used Tailwind CSS for styling and responsive behavior.
- Tested the layout in a local browser.

**Related issue:** Closes #ISSUE_NUMBER

Replace `ISSUE_NUMBER` with the number of the GitHub Issue associated with your task. Using `Closes #123` with the actual issue number automatically closes that issue when the PR is merged.

## Code Review and Merging

Before a pull request is merged, another team member should review the changes.

The reviewer should check that:

- The code is understandable and organized.
- The feature meets the issue's requirements.
- The website looks correct and works as expected.
- The changes do not introduce obvious bugs.
- The feature works with the existing project structure.
- The pull request does not contain unrelated changes.

### If Changes Are Requested

The author should make the requested updates on the same feature branch.

After saving and committing the updates, run:

```bash
git push
```

The existing pull request will update automatically.

### After Approval

Once the required review is complete and any required checks pass, an authorized team member can merge the pull request into `main`.

After merging, the team member can delete the feature branch on GitHub if it is no longer needed.

Other teammates should update their local `main` before beginning their next task:

```bash
git switch main
git pull origin main
```

Then they can create a new feature branch for their next issue.

## Deployment

The website is hosted using GitHub Pages, with GitHub Actions configured to build and deploy the site.

The intended deployment process is:

1. A pull request is reviewed and merged into `main`.
2. A push to `main` triggers the GitHub Actions deployment workflow.
3. The workflow installs dependencies and builds the Tailwind stylesheet.
4. GitHub Pages publishes the site if the workflow succeeds.

### Checking Deployment Status

To check whether a deployment succeeded:

1. Open the repository on GitHub.
2. Click the **Actions** tab.
3. Select the latest **Deploy website** workflow run.
4. Look for a green check mark indicating success.

If a workflow fails, open the run and inspect the failed step. Fix the issue before assuming the website has updated.

The published website URL can be found under **Settings → Pages**.

## Team Guidelines

To keep the project collaborative and maintainable, follow these guidelines:

1. **Use an issue for each task.** Keep work organized and visible to the team.
2. **Create a separate branch for each feature or fix.** Avoid mixing unrelated changes.
3. **Do not push feature work directly to `main`.** Submit a pull request instead.
4. **Review teammates' work constructively.** Ask questions and explain suggestions clearly.
5. **Test before opening a pull request.** Catch simple issues before requesting review.
6. **Communicate early.** Ask for help when requirements or implementation details are unclear.
7. **Keep commits focused.** Each commit should represent a logical set of changes.
8. **Keep secrets out of the repository.** Never commit passwords, access tokens, API keys, or private credentials.
9. **Update your local `main` regularly.** Start new tasks from the latest version.
10. **Keep the website accessible and responsive.** Consider keyboard navigation, readable contrast, and mobile users.

---

## Quick Reference

| Task | Command |
|---|---|
| Update `main` | `git switch main` then `git pull origin main` |
| Create a branch | `git switch -c feature/your-feature` |
| Check current branch | `git branch` |
| Review changes | `git status` and `git diff` |
| Stage changes | `git add .` |
| Commit changes | `git commit -m "Describe your changes"` |
| Push a new branch | `git push -u origin feature/your-feature` |
| Push later updates | `git push` |
| Build Tailwind CSS | `npx @tailwindcss/cli -i ./src/input.css -o ./src/output.css` |
| Watch Tailwind CSS | `npx @tailwindcss/cli -i ./src/input.css -o ./src/output.css --watch` |

**Thanks for contributing to the GDSC William & Mary website!** We are excited to build something great together.
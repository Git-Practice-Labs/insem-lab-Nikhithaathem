Objective

To understand and perform basic Git operations by setting up a repository, creating separate branches for frontend and backend development, and merging them into the main branch.
This lab demonstrates how version control systems help manage multiple parts of a project efficiently.

Tools / Technologies

Git (for version control)

GitHub (for remote repository hosting)

Visual Studio Code / Terminal / Git Bash (for executing Git commands)

(Optional) Docker or Jenkins (for future integration)

Prerequisites

Before starting this lab, ensure the following:

Git is installed on your system
→ Check using:

git --version


GitHub account is created and accessible

VS Code or any code editor installed

Basic Git configuration done:

git config --global user.name "Nikhithaathem"
git config --global user.email "Nikhithaathem@gmail.com"

Steps / Commands
Step 1: Create a new Git repository

Create a new project folder:

mkdir GitBranchDemo
cd GitBranchDemo


Initialize a new Git repository:

git init


✅ Explanation: Initializes an empty Git repository in the folder.

Step 2: Create initial files for the project

Create two folders to represent different parts of the project:

mkdir frontend backend


Add sample files:

echo "<h1>Frontend Page</h1>" > frontend/index.html
echo "console.log('Backend server running');" > backend/app.js


Add these files to Git:

git add .
git commit -m "Initial commit with frontend and backend folders"

Step 3: Create a branch for the frontend
git branch frontend
git checkout frontend


✅ Explanation: Creates a new branch frontend and switches to it.
Modify frontend files:

echo "<p>Welcome to Frontend Development</p>" >> frontend/index.html


Add and commit the changes:

git add .
git commit -m "Updated frontend interface"

Step 4: Create a branch for the backend

Switch back to main:

git checkout main


Create and switch to a backend branch:

git branch backend
git checkout backend


Modify backend files:

echo "console.log('Connected to database');" >> backend/app.js


Add and commit:

git add .
git commit -m "Added backend database connection log"

Step 5: Merge both branches into main

Switch to main:

git checkout main


Merge the frontend branch:

git merge frontend


Then merge the backend branch:

git merge backend


✅ Explanation: Combines both branches into the main branch, integrating frontend and backend work.

Step 6: Push the repository to GitHub

Create a new repository on GitHub (e.g., GitBranchDemo).

Link the local repo to GitHub:

git remote add origin https://github.com/<your-username>/GitBranchDemo.git


Push all branches:

git push -u origin main
git push origin frontend
git push origin backend

Expected Output / Result

The main branch contains merged code from both frontend and backend.

Repository on GitHub should show three branches:

main

frontend

backend

Merging completed successfully without conflicts (if any conflicts occur, they should be resolved manually).

✅ Verification Steps:

Run git branch to list branches.

Run git log --oneline --graph --all to visualize merges.

Check GitHub → Branch dropdown → all branches visible.
Deliverables (What to Push)
Notes / Tips

Always commit your changes before switching branches to avoid losing work.

Use git status frequently to track file states.

In case of merge conflicts:

git status
git diff


Then manually edit conflicting files and commit the resolved versions.

To visualize Git history clearly:

git log --graph --decorate --oneline


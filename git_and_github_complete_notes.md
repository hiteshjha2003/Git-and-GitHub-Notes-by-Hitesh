# Git and GitHub – Complete Notes

## 1. Version Control System (VCS)

- A Version Control System (VCS) is a tool used to track changes made to files and source code over time.
- It helps developers maintain different versions of a project, identify who made changes, compare code, and restore previous versions when required.
- VCS is useful when multiple developers work on the same project because it helps manage changes and avoid overwriting each other's work.
- Example: If you develop an AI chatbot and accidentally introduce a bug, a VCS helps you identify the change and restore an earlier working version.

### Types of Version Control Systems

**1. Centralized Version Control System (CVCS)**

- In a Centralized VCS, the source code and its version history are primarily maintained on a central server.
- Developers connect to the central server to obtain the latest code and submit their changes.
- If the central server becomes unavailable, many collaboration and version-control operations may be affected.
- Examples: SVN (Subversion) and CVS (Concurrent Versions System).

**2. Distributed Version Control System (DVCS)**

- In a Distributed VCS, each developer's local repository can contain the project's complete version history.
- Developers can make commits, create branches, and inspect history without an internet connection.
- Once connected to the internet, developers can synchronize their changes with a remote repository.
- Git is a Distributed Version Control System (DVCS).
- Advantages include offline work, efficient branching, easier collaboration, and local access to project history.

## 2. What Is Git?

- Git is a free, open-source, distributed version control system used to track changes in source code and other files.
- It helps developers maintain project history, create branches, record commits, compare changes, and collaborate with other developers.
- Git can be used through the command line, terminal, or graphical applications.
- Example: If you are developing an AI application, Git can track changes to your Python files, configuration files, and documentation.

## 3. What Is GitHub?

- GitHub is an online platform used to host Git repositories and collaborate on software development projects.
- It allows developers to share code, review changes, create pull requests, report bugs, manage tasks, and automate workflows.
- GitHub stores remote repositories that developers can synchronize with their local repositories.
- GitHub provides collaboration features such as Pull Requests (PRs), Issues, Code Reviews, Branch Protection, and GitHub Actions.
- Example: You develop an AI chatbot on your laptop and upload its Git repository to GitHub so your teammates can review and contribute to the project.

### Difference Between Git and GitHub

- Git is a version control tool that tracks changes and manages repository history.
- GitHub is an online platform that hosts Git repositories and provides collaboration features.
- Git works locally on your computer and supports many operations without internet access.
- GitHub is used to share repositories, review code, manage pull requests, and collaborate with other developers.
- Git commands include `git add`, `git commit`, `git branch`, and `git merge`.
- GitHub features include repositories, pull requests, code reviews, issues, and automated workflows.

## 4. Git Configuration

Before creating commits, developers should configure their Git username and email address.

**Set a username:**

```bash
git config --global user.name "Hitesh"
```

- This sets the default author name used in commit metadata for your current operating-system user.

**Set an email address:**

```bash
git config --global user.email "your-email@example.com"
```

- Replace the example email with your preferred email address.
- You can use an email associated with your GitHub account or a GitHub-provided private email address.

**Check Git configuration:**

```bash
git config --list
```

- Displays applicable Git configuration settings.

**Check only global configuration:**

```bash
git config --global --list
```

- Displays configuration values defined at the global level.

**Check the username and email individually:**

```bash
git config --global user.name
git config --global user.email
```

**Types of Git configuration:**

- System configuration applies to all users on the system, subject to permissions.
- Global configuration applies to the current operating-system user.
- Local configuration applies to the current repository and overrides global settings when the same setting is defined.

Example of repository-specific configuration:

```bash
git config --local user.name "Hitesh Jha"
git config --local user.email "work-email@example.com"
```

Note: Git username and email configure commit metadata. They do not authenticate you to GitHub.

## 5. What Is a Git Repository?

- A repository, commonly called a repo, is a project directory tracked by Git, together with its version-control history and branch information.
- A local repository is stored on your computer.
- A remote repository is hosted on a server or platform such as GitHub.
- Developers make changes and commits locally, then push their commits to the remote repository to share them.

**Initialize a Git repository:**

```bash
mkdir my-project
cd my-project
git init
```

- Creates a directory and initializes Git version control inside it.

**Check repository status:**

```bash
git status
```

- Shows the current branch and the status of modified, staged, and untracked files.

**Connect a local repository to GitHub:**

```bash
git remote add origin https://github.com/USERNAME/REPOSITORY.git
```

- Adds a remote repository named `origin`.
- Replace `USERNAME` and `REPOSITORY` with the correct GitHub account or organization and repository name.

**Check remote repository details:**

```bash
git remote -v
```

- Displays the configured remote repository URLs.

## 6. What Is a Git Branch?

- A branch is an independent line of development within a Git repository.
- Branches allow developers to build features, fix bugs, and test changes without directly modifying another branch.
- Developers can create separate branches for different tasks and integrate the changes after testing and review.
- Example: One developer works on login functionality while another works on dashboard functionality. They can use separate branches and later integrate their changes.

**Common branch names:**

- `main`: Common default branch name, often used for stable or production-ready code.
- `master`: An older or alternative name for the main branch.
- `develop`: An integration branch used in some development workflows.
- `feature/login`: A branch for implementing login functionality.
- `feature/rag-pipeline`: A branch for developing a Retrieval-Augmented Generation pipeline.
- `bugfix/api-error`: A branch for fixing an API bug.
- `hotfix/payment`: A branch for an urgent fix to a released application.

**Important:** Git does not require a branch named `master` or `main`. Both are valid branch names. GitHub commonly uses `main` as the default branch for new repositories, while older repositories may use `master`.

**List local branches:**

```bash
git branch
```

**Check the current branch:**

```bash
git branch --show-current
```

**Create and switch to a new branch:**

```bash
git switch -c feature/login
```

**Switch to an existing branch:**

```bash
git switch main
```

**Rename the current branch:**

```bash
git branch -m main
```

- Renames the current local branch to `main`. If the repository is already shared on GitHub, coordinate the remote branch and default-branch settings before completing the rename.

## 7. What Is a Commit?

- A commit is a recorded snapshot of the staged changes in a Git repository.
- Each commit has a unique identifier, a commit message, author and committer metadata, and references to its parent commit or commits.
- Commits help developers track what changed, when it changed, and why the change was made.
- Example: After adding a RAG pipeline to an AI application, you can create a commit with the message `Add RAG document retrieval`.

**Check changes:**

```bash
git status
```

**View unstaged changes:**

```bash
git diff
```

**Stage a particular file:**

```bash
git add app.py
```

**Stage changes under the current directory:**

```bash
git add .
```

**Create a commit:**

```bash
git commit -m "Add RAG document retrieval"
```

**View commit history:**

```bash
git log --oneline
```

- Good commit messages should describe the purpose of the change.
- Commits should ideally be small, meaningful, and easy to review.
- Never commit passwords, API keys, tokens, or other sensitive credentials.

## 8. Git Workflow: Working Directory, Staging Area, and Repository

Git development commonly involves three areas.

- Working Directory: The location where developers create, modify, and delete project files.
- Staging Area: The area where developers select changes that should be included in the next commit.
- Local Repository: The location where commits and project history are recorded.
- Remote Repository: The shared repository hosted on GitHub or another Git server.

**Basic workflow:**

```bash
# Edit files, then inspect changes
git status

# Stage changes
git add .

# Record a local commit
git commit -m "Describe the changes"

# Upload commits to the remote repository
git push
```

- `git add` stages changes.
- `git commit` records the staged changes locally.
- `git push` uploads commits to the remote repository.
- Committing does not automatically upload code to GitHub.

## 9. What Is a Pull Request (PR)?

- A Pull Request (PR) is a request to review and integrate changes from one branch into another branch.
- Pull Requests are a GitHub collaboration feature, not a Git command.
- Developers typically create a feature branch, make changes, commit them, push the branch to GitHub, and open a PR.
- The PR allows reviewers to inspect the changes, provide feedback, discuss implementation decisions, and check test results before merging.
- Example: A developer creates `feature/rag-pipeline`, implements document retrieval, pushes the branch, and opens a PR to merge it into `main`.

**Typical Pull Request workflow:**

1. Create a feature branch.
2. Write and test the code.
3. Stage and commit the changes.
4. Push the branch to GitHub.
5. Open a Pull Request.
6. Select the base and compare branches.
7. Review the code and automated test results.
8. Address feedback if changes are requested.
9. Obtain the required approvals and pass the required checks.
10. Merge the PR into the target branch.

## 10. Why Should We Avoid Committing Directly to Main?

- In many professional software teams, developers are expected to avoid committing directly to `main`.
- Developers create feature branches and submit PRs instead.
- Code review helps identify bugs, security issues, and problems with code quality.
- Automated tests can run before the changes are merged.
- Branch protection can prevent unauthorized or unreviewed changes.
- Pull Requests maintain a record of discussions, approvals, and decisions.
- Separate branches allow multiple developers to work independently.

Note: This is a common team practice, not a universal Git rule. Direct commits to `main` can be acceptable in personal projects or workflows where the repository policy permits them.

## 11. Base Branch and Compare Branch

When creating a Pull Request, GitHub asks you to select the base and compare branches.

- Base branch: The branch that will receive the proposed changes.
- Compare branch: The branch containing the changes you want to integrate.
- Example: If you want to merge a feature into the main branch, set the base branch to `main` and the compare branch to `feature/rag-pipeline`.
- The direction of integration is from the compare branch into the base branch.
- The base branch does not always have to be `main`. Some teams open feature PRs into `develop` first.

## 12. Pull Request Approval and Rejection

- After a PR is created, reviewers inspect the code and may approve it, comment on it, or request changes.
- Reviewers may request changes when the code contains bugs, security issues, missing tests, incorrect logic, or violations of team coding standards.
- Example: A reviewer may ask the developer to add input validation and unit tests before the PR can be merged.
- The developer should address the feedback, commit the corrections, and push them to the same feature branch.
- New commits pushed to that branch normally update the existing PR automatically.
- Once the required approvals and checks are complete, an authorized contributor can merge the PR.
- A PR may also be declined or closed if the proposed implementation is unnecessary or unsuitable.

**Example feedback:**

> The API endpoint does not validate empty input. Please add input validation and unit tests before merging.

**Commands after fixing the issue:**

```bash
git add .
git commit -m "Add API input validation"
git push
```

Note: Approval does not always mean a PR can be merged immediately. Repository policies may require additional approvals, successful automated checks, or other conditions.

## 13. Important Git Commands

- `git --version`: Displays the installed Git version.
- `git init`: Initializes a new local Git repository.
- `git clone URL`: Clones a remote repository.
- `git status`: Shows the current repository status.
- `git add filename`: Stages a particular file.
- `git add .`: Stages changes under the current directory.
- `git commit -m "message"`: Creates a commit.
- `git log --oneline`: Displays a concise commit history.
- `git branch`: Lists local branches.
- `git switch -c branch-name`: Creates and switches to a new branch.
- `git switch main`: Switches to the `main` branch.
- `git fetch origin`: Downloads remote objects and references without automatically integrating them into the current branch.
- `git pull`: Fetches and integrates remote changes according to the configured strategy.
- `git push`: Uploads local commits to the remote repository.
- `git push -u origin branch-name`: Pushes a branch and sets its upstream tracking branch.
- `git diff`: Displays unstaged changes.
- `git diff --staged`: Displays staged changes.
- `git merge branch-name`: Integrates the specified branch into the current branch.
- `git restore filename`: Discards unstaged modifications to a tracked file.
- `git rm filename`: Removes a tracked file and stages its deletion.

Be careful with commands that discard changes because they can cause you to lose uncommitted work.

## 14. Difference Between Fetch, Pull, and Push

**Git Fetch:**

- `git fetch origin` downloads information about remote commits and branches.
- It does not automatically merge those changes into your current branch.
- It is useful for checking remote updates before integrating them.

**Git Pull:**

- `git pull` fetches remote changes and integrates them into the current branch.
- Depending on configuration, integration may use merging or rebasing.
- It is commonly used to update your local branch with remote changes.

**Git Push:**

- `git push` uploads local commits to the configured remote repository.
- It allows teammates to access the commits you have shared.
- The operation may be rejected if you lack permission or if remote repository rules prevent the update.

## 15. What Is a Merge Conflict?

- A merge conflict occurs when Git cannot automatically reconcile competing changes during a merge, rebase, or another integration operation.
- Conflicts commonly occur when different developers modify the same lines of a file.
- Git requires a developer to inspect the conflicting changes and decide how to combine them.

**Example conflict:**

```text
<<<<<<< HEAD
learning_rate = 0.0001
=======
learning_rate = 0.001
>>>>>>> feature/model-tuning
```

- The conflict markers identify competing versions of the code.
- Open the file and decide which version to retain or whether both changes should be combined.
- Remove the conflict markers, save the file, and test the result.

**Stage the resolved file:**

```bash
git add config.py
```

- If resolving a merge, finish the merge using the instructions Git provides, normally by creating the merge commit if required.
- If resolving a rebase, continue the rebase using `git rebase --continue`.
- A merge conflict is not necessarily a coding error; it means Git needs human input to reconcile the changes.

## 16. Complete Real-World GitHub Workflow

Suppose you are working on an AI chatbot project and want to add a RAG pipeline.

**Step 1: Clone the repository**

```bash
git clone https://github.com/USERNAME/ai-chatbot.git
cd ai-chatbot
```

**Step 2: Check the current branch**

```bash
git branch --show-current
git status
```

**Step 3: Create a feature branch**

```bash
git switch -c feature/rag-pipeline
```

**Step 4: Create or modify your code**

- Add the required Python files and implement the RAG functionality.
- Run the application and relevant tests locally.

**Step 5: Stage and review the changes**

```bash
git status
git diff
git add .
git diff --staged
```

**Step 6: Commit the changes**

```bash
git commit -m "Add RAG document retrieval"
```

**Step 7: Push the feature branch**

```bash
git push -u origin feature/rag-pipeline
```

**Step 8: Create a Pull Request**

- Open the GitHub repository.
- Select the option to create a Pull Request.
- Set the base branch to `main`.
- Set the compare branch to `feature/rag-pipeline`.
- Add a meaningful title and description.
- Submit the PR for review.

**Step 9: Address review feedback**

```bash
git add .
git commit -m "Improve RAG input validation"
git push
```

- The existing PR is normally updated automatically when new commits are pushed to its source branch.

**Step 10: Merge the Pull Request**

- After the required reviews and checks are complete, an authorized contributor merges the PR.
- The target branch now contains the integrated changes.

## 17. Multiple Developers Working on the Same Project

- Developer A creates `feature/anomaly-detection` and implements anomaly detection.
- Developer B creates `feature/monitoring-api` and develops the REST API.
- Both developers make commits on their own branches.
- Both developers push their branches to GitHub.
- Each developer opens a PR for review.
- Reviewers check the code and automated tests.
- After the required approvals, the changes are merged into the appropriate target branch.
- If conflicting changes occur, the developers resolve the conflicts before integration.

This workflow supports parallel development while maintaining code quality and traceability.

## 18. Difference Between Commit, Push, Pull Request, and Merge

- Commit: Records staged changes in the local repository.
- Push: Uploads local commits to a remote repository.
- Pull Request: Requests review and integration of changes into a target branch.
- Merge: Integrates changes from one branch into another branch.

**Typical sequence:**

`Edit Code → Stage Changes → Commit → Push → Create PR → Review → Merge`

A Pull Request is not the same as a merge. Opening a PR proposes a change, while merging integrates the change into the target branch.

## 19. Quick Revision Notes

- VCS: A system used to track and manage changes to files.
- CVCS: A version control system that relies primarily on a central server.
- DVCS: A version control system in which each clone can contain the repository's history.
- Git: A distributed version control system.
- GitHub: An online platform for hosting Git repositories and collaborating on projects.
- Repository: A project and its version-control history.
- Branch: An independent line of development.
- Commit: A recorded snapshot of staged changes.
- Push: Uploads local commits to a remote repository.
- Fetch: Downloads remote repository information without automatically integrating it into the current branch.
- Pull: Fetches and integrates remote changes.
- Pull Request: A request to review and integrate changes between branches.
- Merge: Integrates changes from one branch into another.
- Merge Conflict: A situation in which Git requires help reconciling competing changes.
- `main` and `master`: Both are valid branch names; neither is mandatory in Git.
- Protected Branch: A branch with repository rules that restrict how changes can be made or merged.

**Best Practice:** In a team project, create a separate feature branch, write and test your code, commit meaningful changes, push the branch to GitHub, open a Pull Request, address review feedback, and merge only after satisfying the team's approval and testing requirements.

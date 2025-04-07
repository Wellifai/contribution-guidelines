# Contribution Guidelines

Welcome to our contribution guide repository!  
This repository provides guidelines on how to contribute to our company projects.
Right now this repository describes what we should strive for. Given our team size, we have to cut corners, so not everything listed below will be followed to the letter. Please use common sense :)

## Table of contents
1. [Steps to contribute to a GitHub repository](#1-steps-to-contribute-to-a-github-repository)
2. [Commit messages](#2-commit-messages)
3. [Code quality](#3-code-quality)
4. [Semantic versioning](#4-semantic-versioning)

## 1. Steps to contribute to a GitHub repository
If you are allowed to commit changes directly, do that. If not, you should follow these rules:  
  
1. **Fork the repository**: Create a personal copy
2. **Clone the fork**: Clone your fork to your local machine.
3. **Create a branch**: Create a new branch for your feature or bug fix.
4. **Make your changes**: Implement your changes in the new branch, test them
5. **Write meaningful commit messages**: Follow our commit message conventions.
6. **Push your changes**: Push your changes to your forked repository.
7. **Create a pull request**: Submit a pull request to the original repository.

## 2. Commit messages
### 2.1 Conventional commits
[Conventional commits](https://www.conventionalcommits.org/en/v1.0.0/) should be used.
Please let me know if you think there is a need for a new type.  
* build: Changes related to the build system or external dependencies.
* chore: Regular maintenance, tasks, or minor updates that are not related to the main codebase.
* ci: Changes to the CI (Continuous Integration) configuration and scripts.
* deps: Updating dependencies.
* docs: Documentation-related changes, including adding, updating, or deleting documentation.
* feat: The introduction of a new feature for the user or improvement to existing features.
* fix: Bug fixes or corrections to existing code.
* merge: Signifies the merging of one branch into another.
* perf: Performance-related improvements or optimizations.
* refactor: Code restructuring that doesn't change its external behavior but improves its internal structure.
* release: Version release-related changes.
* revert: Reverting a previous commit.
* security: Fixes or improvements related to security vulnerabilities.
* style: Code style changes, such as formatting, indentation, or naming conventions.
* test: Adding or modifying tests.  

### 2.2 Scope
The scope specifies the section of the codebase affected by the changes. It provides additional contextual information and helps in understanding the impact of the commit. The scope is optional but recommended for clarity.
The scope should be the name of the module affected (as perceived by the person reading the changelog generated from commit messages).

Example scopes (this is not a final list):
- **ui**: Changes affecting the user interface. It could be more specific, mentioning one of the main screens, or a popup screen:
  - **ui-splash**: splash screen
  - **ui-chat**: main screen #1
  - **ui-health**: main screen #2
  - **ui-fitness**: main screen #3
  - **ui-lifestyle**: main screen #4
  - **ui-settings**: main screen #5
- **api**: Modifications to the API. Again, it could be more specific
- **auth**: Updates related to authentication.
- **navigation**: changes to navigation mechanism/routes
- **database**: Changes in database-related code.
- **config**: Configuration file updates or changes.
- **comp-&lt;component-name&gt;**: changes to a specific component

Commit message format:
```
<type>[optional scope]: <description>
[ne empty line if 'body' is specified]
[optional body]
[optional footer(s)]
```

Commit message example:  
```
feat(parser): add ability to parse arrays

This feature allows the user to parse arrays, enabling support for complex data structures.

BREAKING CHANGE: The parse method now returns an array instead of a single object.
```

###Best practices
* Single Responsibility: Each commit should ideally address a single problem or add one feature. Avoid bundling multiple changes into one commit (exceptions are possible, for example, multiple minor changes in the same module could be bundled in one commit).
* Commit Message Accuracy: A commit should only include changes that are described in the commit message. Do not include unrelated fixes or features.
* Minimize File Changes: Keep the changes (number of files changed) in each commit as minimal as possible, focusing only on the specific issue or feature being addressed.
* Readable Commits: Ensure that each commit is readable and understandable on its own, making it easier for others to review and understand the changes.
* Consistent Style: Follow the project's coding style and guidelines consistently across all commits.
* Incremental Changes: Keep commits incremental and focused, avoiding large sweeping changes to facilitate easier code review and debugging.
* Tested Changes: Ensure that changes are tested and do not break existing functionality before committing.
* Documentation: Update relevant documentation when making changes that impact the project's usage or setup.

## 3. Code quality
Maintaining high code quality is crucial for the success and maintainability of our project.

### Python
* Follow the [PEP8](https://pep8.org/) style guide for Python code. This includes guidelines on naming conventions, code layout, indentation, and more.

### JavaScript/TypeScript
* [Airbnb JavaScript Style Guide](https://github.com/airbnb/javascript) for JavaScript and TypeScript code.
* [TypeScript Handbook](https://www.typescriptlang.org/docs/handbook/intro.html) guidelines.
* For TSX (TypeScript with JSX), follow best practices for React and Expo projects as outlined in the [React Documentation](https://reactjs.org/docs/getting-started.html) and [Expo Documentation](https://docs.expo.dev/).

### General Guidelines
* Ensure your code is well-documented and follows the coding standards.
* ~~Write unit tests for new features and bug fixes.~~	(testing will be decided later, for now, it is manual)
* Perform regular code reviews to maintain high code quality/consistency. (right now code reviews are done when merging pull requests into the master branch)
* Use linters and formatters to automatically enforce coding standards. Examples:
  - Use ESLint for JavaScript/TypeScript: [ESLint](https://eslint.org/)
  - Use Prettier for code formatting: [Prettier](https://prettier.io/)

Note: Please only lint the code that you commit, and the files you work on. Don't lint everything in the repository. Different people use different tools/settings for linting.  
Note: exact linting/formatting/commenting rules will be decided later. Please don't go overboard with commenting everything :)

## [4. Semantic versioning](https://semver.org/) 
This part is not implemented/strictly followed yet.  
  
The version number should correspond to Major/Minor/Patch:  
- **Major**: Incremented for incompatible API changes.
- **Minor**: Incremented for backward-compatible functionality.
- **Patch**: Incremented for backward-compatible bug fixes.

### Examples
Assume the current version of a project is `1.4.2`:  
- If a new feature is added in a backward-compatible manner, the new version will be `1.5.0`.
- If a bug is fixed without affecting the API, the new version will be `1.4.3`.
- If there is an incompatible API change, the new version will be `2.0.0` (really think this through!).

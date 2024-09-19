## Contribution Guidelines

Thank you for your interest in contributing to our package! This document outlines the tools and steps to follow to ensure a smooth and consistent workflow.

## Contribution Workflow

1. **Fork and Clone**: Fork the repository and clone it to your local machine.
    ```bash
    git clone https://github.com/<your-username>/django-sage-invoice.git
    cd django-sage-invoice
    ```


2. **Initialize Git Flow**: Set up Git Flow to manage your branches efficiently.
    ```bash
    git flow init
    ```
    Follow the prompts to configure Git Flow. The default options usually suffice.

3. **Create a Branch**: Create a new branch for your feature or bugfix using Git Flow.

    - **Creating a Feature Branch**:
      ```bash
      git flow feature start your-feature-name
      ```
      This will create and check out a new branch from the `develop` branch.

    - **Creating a Bugfix Branch**:
      ```bash
      git flow bugfix start your-bugfix-name
      ```
      This will create and check out a new branch specifically for the bugfix.

4. **Install Dependencies**: Use Poetry to install dependencies.
    ```bash
    poetry install
    ```

5. **Write Code and Tests**: Make your changes and write tests for your new code.

6. **Run Code Quality Checks**: Ensure code quality with pre-commit, Ruff, and Pylint.
    ```bash
    poetry run pre-commit run --all-files
    poetry run ruff check sage_invoice/ --fix
    poetry run black sage_invoice/
    poetry run isort sage_invoice/
    poetry run pylint sage_invoice/
    poetry run bandit -r sage_invoice/ -c pyproject.toml
    ```

7. **Run Tests**: Ensure all tests pass using Poetry.
    ```bash
    poetry run pytest
    ```

8. **Commit Changes**: Use Commitizen to commit your changes.
    ```bash
    cz commit
    ```

9. **Push and Create a PR**: Push your changes and create a pull request.
    ```bash
    git push origin feature/your-feature-name
    ```

10. **Bump Version**: Use Commitizen to bump the version.
    ```bash
    cz bump
    ```

11. **Generate Changelog**: Use Commitizen to generate the changelog.
    ```bash
    cz changelog
    ```

12. **Export Dependencies**: Export dependencies for development and production.
    ```bash
    poetry export -f requirements.txt --output requirements/req.txt --without-hashes
    poetry export -f requirements.txt --dev --output requirements/dev.txt --without-hashes
    ```

## Commitizen Message Rule

Commitizen follows the Conventional Commits specification. The commit message should be structured as follows:

```
<type>[optional scope]: <description>

[optional body]

[optional footer(s)]
```

Here are 10 examples of commit messages following the Commitizen Conventional Commits specification:

### 1. Initialization of core
```
feat(core): initialize the core module

- Set up the core structure
- Added initial configurations and settings
- Created basic utility functions
```

### 2. Release with build and tag version
```
build(release): build and tag version 1.0.0

- Built the project for production
- Created a new tag for version 1.0.0
- Updated changelog with release notes
```

### 3. Adding a new feature
```
feat(auth): add user authentication

- Implemented user login and registration
- Added JWT token generation and validation
- Created middleware for protected routes
```

### 4. Fixing a bug
```
fix(api): resolve issue with data fetching

- Fixed bug causing incorrect data responses
- Improved error handling in API calls
- Added tests for the fixed bug
```

### 5. Update a doc (Sphinx)
```
docs(sphinx): update API documentation

- Updated the Sphinx documentation for API changes
- Added examples for new endpoints
- Fixed typos and formatting issues
```

### 6. Update dependencies (packages)
```
build(deps): update project dependencies

- Updated all outdated npm packages
- Resolved compatibility issues with new package versions
- Ran tests to ensure no breaking changes
```

### 7. Update version for build and publish
```
build(version): update version to 2.1.0 for build and publish

- Incremented version number to 2.1.0
- Updated package.json with the new version
- Prepared for publishing the new build
```

### 8. Adding unit tests
```
test(auth): add unit tests for authentication module

- Created tests for login functionality
- Added tests for registration validation
- Ensured 100% coverage for auth module
```

### 9. Refactoring codebase
```
refactor(core): improve code structure and readability

- Refactored core module to enhance readability
- Extracted utility functions into separate files
- Updated documentation to reflect code changes
```

### 10. Improving performance
```
perf(parser): enhance parsing speed

- Optimized parsing algorithm for better performance
- Reduced the time complexity of the parsing function
- Added benchmarks to track performance improvements
```

These examples cover various types of commits such as feature additions, bug fixes, documentation updates, dependency updates, versioning, testing, refactoring, and performance improvements.
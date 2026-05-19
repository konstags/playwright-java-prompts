
# Prompts for generating Playwright Java framework

**Beginner-friendly AI prompts** for setting up a Playwright Java test framework with Maven, TestNG, and Allure reporting.

> **Note:** The generated Playwright Java project is created as a sibling folder.

## 📋 What This Repo Contains

- ✅ Sequential Copilot prompts for project setup
- ✅ Planning mode guidance and mode-switching instructions  
- ✅ Step-by-step setup

## 🚀 Quick Start

### 1. Install Copilot CLI

Install and setup: [github.com/features/copilot/cli](https://github.com/features/copilot/cli)


### 2. Run the First Prompt (Recommended: 00a)

```bash
# Navigate to this repo
cd /path/to/playwright-java-prompts

# Open Copilot CLI in interactive mode
copilot

# Run the first prompt (guided beginner path)
@playwright-java-prompts/prompts/00a-beginner-guided-start.txt

# Optional: fast path for experienced users
# @playwright-java-prompts/prompts/00b-fast-start.txt
```

### 3. Complete Prompts 01-03

In the same manner, starting with "@" run prompts 01, 02, and 03 - they will do the following:

- `01-pw-dependencies.txt`: Verifies and prepares required tools and dependencies.
- `02-create-project.txt`: Creates the `playwright-java-automation` project skeleton and base configuration.
- `03-apply-generated-project-templates.txt`: Applies template files (`.github/copilot-instructions.md`, `.github/prompts/`, `skills/`) to the generated `playwright-java-automation` project.

After prompts 00-03 are complete, switch to the new project folder: `playwright-java-automation`.

## 📦 Generated Project Structure

The generated project should follow this structure:

```
playwright-java-automation/
├── pom.xml                            # Maven configuration
├── src/
│   ├── test/
│   │   ├── java/
│   │   │   └── com/company/tests/     # Test classes
│   │   └── resources/                 # Test configuration files
│   └── main/
│       └── java/                      # Page objects, utilities
├── target/                            # Build output
├── allure-results/                    # Allure test reports
├── README.md                          # Project-specific documentation
├── .github/
│   └── copilot-instructions.md        # Custom Copilot instructions (optional)
│   └── prompts/
│       ├── test-generation.md         # Test generation helper prompt
│       ├── page-object-generation.md  # Page object helper prompt
│       └── test-utility-generation.md # Utility helper prompt
└── skills/                            # Custom Copilot skills (optional)
    ├── pw-test-patterns.md            # Playwright patterns
    └── testng-fixtures.md             # TestNG patterns
```

### 4. Execute remaining prompts

In the new project, continue with prompts 04-07.

- `04-playwright-cli-saucedemo.txt`: Interactive Playwright CLI walkthrough (SauceDemo example). Exploration and selector verification only; no automatic test generation. Optional learning step.
- `05a-jira-to-playwright-test.txt`: Jira-driven Playwright CLI execution prompt. Asks for a Jira ticket ID, shows planned scenarios for user approval, then runs them one-by-one with Playwright CLI. No Java code generation in this step.
- `05b-file-to-playwright-test.txt`: File-driven fallback prompt for the same workflow when Jira is not available. Uses a plain-English `.txt` file as the source input.
- `06-debugging-and-reports.txt`: Adds debugging helpers, failure artifacts, and reporting setup improvements.
- `07-test-data-parameterization.txt`: Refactors tests to use external test data and TestNG `@DataProvider` patterns.


## 🔗 Resources

- [GitHub Copilot CLI Docs](https://github.com/features/copilot/cli)
- [Playwright Java Docs](https://playwright.dev/java/)
- [Maven Guide](https://maven.apache.org/)
- [TestNG Docs](https://testng.org/)
- [Allure Report Docs](https://docs.qameta.io/allure/)



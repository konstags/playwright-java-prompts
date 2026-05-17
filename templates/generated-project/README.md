# My Playwright Java Project

Playwright Java testing project with TestNG and Allure reporting.

## Project Structure

```
.
├── pom.xml                     # Maven dependencies and configuration
├── src/
│   ├── test/
│   │   ├── java/
│   │   │   └── com/company/
│   │   │       ├── pages/      # Page objects
│   │   │       ├── tests/      # Test classes
│   │   │       └── utils/      # Utilities
│   │   └── resources/          # Test configuration
│   └── main/
│       └── java/               # Reusable code
├── allure-results/             # Allure test reports
├── .github/
│   └── copilot-instructions.md # Copilot guidance (see for instructions)
│   └── prompts/
│       ├── prompts.md          # Reusable prompt index
│       ├── test-generation.md
│       ├── page-object-generation.md
│       └── test-utility-generation.md
└── skills/                     # Domain knowledge files
    ├── pw-test-patterns.md
    ├── testng-fixtures.md
    └── allure-annotations.md
```

## Getting Started

### Prerequisites
- Java 11+
- Maven 3.6+
- Playwright Java (configured in pom.xml)

### Run Tests

```bash
# Run all tests
mvn test

# Run specific test class
mvn test -Dtest=LoginTests

# Run tests with Allure reporting
mvn test
allure serve allure-results
```

## Using with Copilot

Refer to:
- **`.github/copilot-instructions.md`** - Custom instructions for this project
- **`skills/`** - Domain knowledge for better code generation
- **`.github/prompts/prompts.md`** - Prompt index for available helper prompts
- **`.github/prompts/test-generation.md`** - Generate new test classes
- **`.github/prompts/page-object-generation.md`** - Generate page object classes
- **`.github/prompts/test-utility-generation.md`** - Generate shared test utilities

This helps Copilot understand your project conventions and generate consistent code.

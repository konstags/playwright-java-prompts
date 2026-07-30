# Playwright Java Testing Patterns

## BaseTest Pattern (Headed/Headless Toggle)

All test classes should extend `BaseTest`. The browser mode is controlled by the `-Dheaded=true` system property:

> **Location:** Always place `BaseTest.java` in `src/test/java/com/company/base/` — **never** in `src/main/java`.
> TestNG annotations (`@BeforeMethod`, `@AfterMethod`) require TestNG on the classpath, which is a `test`-scoped dependency in Maven.
> Placing `BaseTest` in `src/main` causes a compilation error because `org.testng.annotations` is not available in the main compile scope.

```java
// src/test/java/com/company/base/BaseTest.java
package com.company.base;

public class BaseTest {

    protected Playwright playwright;
    protected Browser browser;
    protected BrowserContext context;
    protected Page page;

    @BeforeMethod
    public void setUp() {
        playwright = Playwright.create();
        boolean headless = !Boolean.parseBoolean(System.getProperty("headed", "false"));
        browser = playwright.chromium().launch(new BrowserType.LaunchOptions().setHeadless(headless));
        context = browser.newContext();
        page = context.newPage();
    }

    @AfterMethod
    public void tearDown() {
        if (context != null) context.close();
        if (browser != null) browser.close();
        if (playwright != null) playwright.close();
    }
}
```

Run with visible browser: `mvn -s settings-central.xml test -Dheaded=true`
Run headless (default): `mvn -s settings-central.xml test`

## Common Test Structure

```java
@Feature("Login")
public class LoginTests {
    
    @BeforeMethod
    public void setup() {
        // Initialize browser and navigate
    }
    
    @AfterMethod
    public void teardown() {
        // Close browser and cleanup
    }
    
    @Test(groups = "smoke")
    @Severity(SeverityLevel.CRITICAL)
    public void testValidLogin() {
        // Test implementation
    }
}
```

## Page Object Pattern

- Create separate classes for each page/component
- Use private selectors with public methods
- Method names should describe user actions (e.g., `clickLoginButton()`, `fillUsername()`)
- Handle waits and synchronization in page objects

## Best Practices

- Use soft assertions for multiple validations
- Group related tests using TestNG groups
- Annotate all tests with @Feature and @Story for Allure reporting
- Use data providers for parameterized tests
- Keep test methods focused on single scenarios

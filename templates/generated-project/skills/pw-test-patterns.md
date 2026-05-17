# Playwright Java Testing Patterns

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

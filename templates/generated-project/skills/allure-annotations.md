# Allure Reporting Best Practices

## Essential Annotations

```java
@Feature("User Authentication")
@Story("User login with valid credentials")
@Severity(SeverityLevel.CRITICAL)
@Test
public void testLoginSuccess() {
    // Implementation
}
```

### Feature
Categorize tests by major features or modules.
```java
@Feature("Login")
@Feature("Dashboard")
@Feature("Checkout")
```

### Story
Describe the specific user story or scenario.
```java
@Story("User can login with email and password")
```

### Severity Levels
Use appropriate severity levels:
- `BLOCKER` - Critical functionality broken
- `CRITICAL` - Major feature not working
- `MAJOR` - Significant issue
- `MINOR` - Minor issue
- `TRIVIAL` - Cosmetic issues

### Steps
Document test steps for better reporting:
```java
@Step("Click login button")
public void clickLogin() {
    page.click("[data-testid='login-btn']");
}
```

## Attachment Examples

```java
@Attachment(value = "Page screenshot", type = "image/png")
public byte[] takeScreenshot() {
    return page.screenshot();
}

@Attachment(value = "Test data", type = "text/plain")
public String attachTestData(String data) {
    return data;
}
```

## Test Configuration

All tests should have:
- `@Feature` annotation
- `@Story` or clear description
- `@Severity` level assignment
- Relevant `@Test` groups
- Steps annotated with `@Step` for clarity

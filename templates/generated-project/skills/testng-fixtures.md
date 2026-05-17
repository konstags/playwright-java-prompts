# TestNG Fixtures and Setup Patterns

## Common Setup/Teardown Methods

```java
@BeforeClass
public static void setupClass() {
    // One-time setup for entire class
    // Load configuration, initialize static resources
}

@BeforeMethod
public void setupTest() {
    // Setup before each test method
    // Initialize browser, navigate to base URL
    browser = playwright.chromium().launch();
    page = browser.newPage();
    page.navigate("https://example.com");
}

@AfterMethod
public void teardownTest() {
    // Cleanup after each test
    page.close();
    browser.close();
}

@AfterClass
public static void teardownClass() {
    // Final cleanup
}
```

## Data Providers

```java
@DataProvider(name = "loginData")
public Object[][] getLoginData() {
    return new Object[][] {
        {"user@example.com", "password123"},
        {"admin@example.com", "adminPass456"}
    };
}

@Test(dataProvider = "loginData")
public void testLogin(String email, String password) {
    // Test with different data
}
```

## Base Test Class

Create a BaseTest class that:
- Extends TestBase if using a framework
- Handles browser initialization and cleanup
- Provides common assertion helpers
- Manages test configuration

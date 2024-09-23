# 04: Implementing Test Automation - 150 minutes

## Keywords:
risk, test fixture

## Learning Objectives for Chapter 4:




### 4.1 Test Automation Development
- TAE-4.1.1 (K3) Apply guidelines that support effective test automation pilot and deployment activities
### 4.2 Risks Associated with Test Automation Development
- TAE-4.2.1 (K4) Analyze deployment risks and plan mitigation strategies for test automation
### 4.3 Test Automation Solution Maintainability
- TAE-4.3.1 (K2) Explain which factors support and affect test automation solution maintainability

## 4.1 Test Automation Development
### 4.1.1 Apply Guidelines that Support Effective Test Automation Pilot and Deployment Activities

It is important to define the scope of validation for a **test automation pilot**. A pilot project does not take a
long time to conduct, but the outcome may have a significant impact on the direction that the project takes.

Based on the gathered information about the SUT and project requirements, the following factors should be evaluated to establish guidelines for **optimizing test automation efforts**:

- **Programming language(s):** Choose the programming language(s) that align with the SUT and the team's expertise.
- **Suitable tools:** Evaluate commercial off-the-shelf or open-source tools that meet the project’s needs.
- **Test levels:** Identify the test levels (e.g., unit, integration, system, acceptance) to be covered.
- **Test cases:** Select the specific test cases to automate, focusing on high-priority and frequently executed ones.
- **Test case development approach:** Define the approach for developing test cases (e.g., data-driven, keyword-driven, BDD) based on project needs and team skillset.

Based on the bullet points listed above, TAEs can establish an **initial test automation approach.** Multiple prototypes can be developed to compare the pros and cons of different strategies, helping determine the best path forward.

#### Key Steps in the Pilot:

- **Define timelines**: Set realistic schedules and monitor progress regularly to identify and mitigate risks.
- **CI/CD Integration**: During the pilot, integrate the test automation with CI/CD to identify issues early, whether in the SUT, TAS, or tool integration.
- **Adjust CI/CD setup**: As test cases grow, consider modifying the CI/CD setup to run tests in different ways and at varied times.

#### Non-technical aspects to evaluate:

- Team knowledge and experience
- Team structure
- Licensing and organization policies
- Planned testing types and targeted test levels

After completing the pilot, TAEs and test managers should evaluate the outcomes to determine success and make informed decisions on the next steps.

### Example* Test Automation Pilot for a Financial Application

### Scenario:
A team is preparing to automate testing for a financial application that processes transactions. They are conducting a **test automation pilot** to validate the effectiveness of their approach before rolling it out across the entire system. The goal is to automate critical test cases, optimize CI/CD integration, and establish a clear strategy for scaling automation.

#### Guidelines for Optimizing Test Automation:

1. **Programming Language(s):**
   - The financial application is written in **Java**, and the team has expertise in Java. Therefore, the test automation will also be implemented in Java using frameworks like **Selenium** for UI tests and **JUnit** for unit tests.

2. **Suitable Tools:**
   - After evaluating both open-source and commercial tools, the team decides to use **Selenium** for web-based UI automation, **TestNG** for test management, and **Maven** for dependency management and CI/CD integration.
   - They also consider integrating **Appium** for mobile testing in the future.

3. **Test Levels:**
   - The pilot focuses on automating **system-level** and **integration-level** tests, particularly around transaction validation and user workflows, such as transferring funds and checking balances.

4. **Test Cases:**
   - High-priority test cases include:
     - **Validating successful transactions** under different scenarios (e.g., different currencies, amounts).
     - **Edge cases** such as exceeding transaction limits.
     - **Frequently used workflows**, like logging in, making transfers, and generating reports.

5. **Test Case Development Approach:**
   - The team adopts a **data-driven** approach for test cases involving multiple inputs, such as validating transactions for various account types.
   - For more complex workflows, they will use **keyword-driven testing**, allowing business analysts to define steps in natural language.

#### Initial Test Automation Approach:

The team creates two **prototypes** to compare strategies:
- **Prototype 1:** Uses data-driven testing for transaction scenarios.
- **Prototype 2:** Implements keyword-driven testing for end-to-end workflows like account management.

They compare the pros and cons of both approaches to determine which is easier to maintain, scales better, and fits with the team’s skillset.

#### Key Steps in the Pilot:

1. **Define Timelines:**
   - The team sets a **4-week pilot schedule** with weekly progress reviews.
   - They aim to automate 10 key test cases and integrate the tests into the CI/CD pipeline by the end of the pilot.

2. **CI/CD Integration:**
   - The pilot includes integrating test automation with the **Jenkins CI/CD pipeline** to ensure automated tests run with each build. This helps identify issues early, especially in core transaction flows.

3. **Adjust CI/CD Setup:**
   - As test cases grow, the team configures Jenkins to:
     - Run smoke tests on every commit.
     - Execute more comprehensive regression tests nightly.

#### Non-technical Aspects:

- **Team Knowledge & Experience:**
   The team has strong Java and Selenium experience but less exposure to keyword-driven testing. Training sessions are scheduled for team members to familiarize them with this approach.

- **Team Structure:**
   Dedicated roles for test automation engineers (TAEs), developers, and business analysts are defined. Business analysts will collaborate closely to write keyword-driven test scenarios.

- **Licensing & Organization Policies:**
   The company prefers using open-source tools, so the decision to use Selenium, TestNG, and Jenkins aligns with company policies.

- **Planned Testing Types:**
   Focus on system, integration, and regression testing during the pilot. Unit testing is already covered separately by developers.

#### Post-Pilot Evaluation:

After the 4-week pilot, the team evaluates:
- The effectiveness of the automation strategy.
- The ease of maintaining and scaling test cases.
- The success of integrating automation into the CI/CD pipeline.

Based on this evaluation, the team refines the automation approach, decides on further tool integrations (e.g., Appium for mobile), and plans to expand the automation effort across additional modules of the financial application.

By following these **guidelines**, the pilot helps ensure that test automation for the financial application is efficient, scalable, and aligned with both technical and business needs.



## 4.2 Risks Associated with Test Automation Development
### 4.2.1 Analyze deployment risks and plan mitigation strategies for test automation


When designing the Test Automation Framework (TAF) architecture, **interfacing with the System Under Test (SUT) is a key consideration.** After defining this interface, other essential components like **packaging**, **test logging**, and the test harness tools can be selected.

During the pilot implementation, the **expansion and maintenance** of the test automation code are vital to consider. These aspects play a significant role in the pilot's evaluation and can influence the final decision.

Key **deployment risks** identified during the pilot may include:

- **Firewall openings**: Ensuring proper network access and security configurations.
- **Resource utilization**: Monitoring system resources such as CPU and RAM to ensure efficient operation without overloading the system.

Preparation is essential for addressing **deployment risks** such as firewall issues, resource utilization, network connection, and reliability. Although not directly tied to test automation, TAEs must ensure that these factors are managed to maintain reliable and effective quality gates throughout the development process.

For example, in mobile test automation, real devices need to meet certain conditions:

- Devices should be powered on and have sufficient battery power to run tests.
- They must be connected to a network and have access to the SUT.

Key **technical deployment risks** to consider include:

- **Packaging**: Ensuring smooth integration and distribution of test components.
- **Logging**: Capturing detailed logs for debugging and reporting.
- Test structuring: Organizing tests for maintainability and scalability.
- **Updating**: Managing updates to ensure tests remain relevant with system changes.

Addressing these factors is crucial for achieving successful and reliable automation.

#### Packaging
In test automation, packaging must be considered with the same importance as version control for the SUT. Testware, including scripts and test assets, may need to be stored in a version-controlled repository to allow easy sharing across an organization, either **on-premises** or in the **cloud**.

#### Logging
Effective test logging is crucial for understanding test results. Different logging levels provide various details during test execution:

- **Fatal**: Logs critical errors that may abort test execution.
- **Error**: Logs conditions that cause a test case to fail.
- **Warn**: Logs unexpected conditions that don’t break test flow but are noteworthy.
- **Info**: Logs basic information about test execution steps.
- **Debug**: Logs detailed information useful for investigating failures.
- **Trace**: Logs the most detailed execution data, beyond Debug.

#### Test Structuring
The **test harness** and **test fixtures** are core components of the Test Automation System (TAS). These control the test environment and data, ensuring the automation is reliable, repeatable, and atomic. Key structuring elements include:

- **Preconditions and postconditions**: Defined to prepare and clean up after tests.
- **Test suites**: Grouping test cases for better organization and execution management.

These are vital for scalable, maintainable automation frameworks and must be evaluated in any pilot project.

#### Updating
Automatic updates to the test harness (e.g., agents) and devices pose a risk. These can be mitigated by:

- Ensuring **power supplies** are stable.
- Maintaining proper **network connections**.
- Implementing **device configuration plans** to manage updates and version changes.

# 4.1.1 Analyze Deployment Risks and Plan Mitigation Strategies for Test Automation

When designing the **Test Automation Framework (TAF) architecture**, **interfacing with the System Under Test (SUT)** is a key consideration. Once this interface is defined, other essential components like **packaging**, **test logging**, and **test harness tools** can be selected.

During the pilot implementation, the **expansion and maintenance** of the test automation code are crucial. These aspects influence the pilot’s evaluation and may impact the final decision.

### Key Deployment Risks

Identified risks during the pilot may include:

- **Firewall openings**: Ensuring proper network access and security configurations.
- **Resource utilization**: Monitoring CPU, RAM, and other resources to prevent system overload.

Preparation is critical to address **deployment risks** like firewall issues, resource utilization, network connections, and reliability. Though not directly tied to test automation, TAEs must manage these factors to maintain effective quality gates throughout development.

---

### Example*: Mobile Test Automation Deployment Risks

For mobile test automation, real devices must meet certain conditions:
- Devices should be **powered on** and have sufficient battery power to run tests.
- Devices must be **connected to a network** with access to the SUT.

#### Key Technical Deployment Risks

Key technical risks to consider during deployment include:

- **Packaging**: Ensuring smooth integration and distribution of test components.
- **Logging**: Capturing detailed logs for debugging and reporting.
- **Test structuring**: Organizing tests for maintainability and scalability.
- **Updating**: Managing updates to keep tests relevant with system changes.

Addressing these factors is crucial for achieving successful and reliable automation.

#### Packaging

In test automation, **packaging** should be treated with the same importance as version control for the SUT. Testware, including scripts and assets, may need to be stored in a **version-controlled repository** to facilitate easy sharing across an organization, either **on-premises** or in the **cloud**.

#### Logging

Effective **test logging** is vital for understanding test results. Different logging levels provide varying details during test execution:

- **Fatal**: Logs critical errors that may abort test execution.
- **Error**: Logs conditions that cause a test case to fail.
- **Warn**: Logs unexpected conditions that don’t break test flow but are noteworthy.
- **Info**: Logs basic information about test execution steps.
- **Debug**: Logs detailed information useful for investigating failures.
- **Trace**: Logs the most detailed execution data, beyond Debug.

#### Test Structuring

The **test harness** and **test fixtures** are core components of the Test Automation System (TAS). These components control the test environment and data, ensuring automation is **reliable, repeatable, and atomic**. Key structuring elements include:

- **Preconditions and postconditions**: Defined to prepare and clean up after tests.
- **Test suites**: Grouping test cases for better organization and execution management.

These are vital for creating **scalable and maintainable** automation frameworks and must be evaluated in any pilot project.

#### Updating

Automatic updates to the test harness (e.g., agents) and devices pose a risk. These can be mitigated by:

- Ensuring **power supplies** are stable.
- Maintaining proper **network connections**.
- Implementing **device configuration plans** to manage updates and version changes.


## 4.3 Test Automation Solution Maintainability
### 4.3.1 Explain which factors support and affect test automation solution maintainability

Maintainability is significantly influenced by programming standards and the expectations that Test Automation Engineers (TAEs) have of each other. A golden rule is to adhere to the **Clean Code Principles** by Robert C. Martin, as outlined in *Clean Code: A Handbook of Agile Software Craftsmanship* (2008). Key principles include:

- **Common Naming Conventions**: Use meaningful names for classes, methods, and variables (e.g., `loginButton`, `resetPasswordButton`) to enhance readability and understanding.
- **Logical Project Structure**: Maintain a consistent and logical structure for the project.
- **Avoid Hardcoding**: Do not embed values directly in the code. Use data-driven testing to source test data from a common, easily maintained location. This reduces maintenance overhead and allows for flexibility.
- **Limit Input Parameters**: Avoid methods with too many input parameters to enhance clarity.
- **Shorten Methods**: Keep methods concise to improve readability and maintainability.
- **Use Logging**: Implement logging to aid in debugging and understanding test execution flow.
- **Leverage Design Patterns**: Utilize design patterns where beneficial to create structured, maintainable test automation code.
- **Focus on Testability**: Design code with testing in mind.

#### Naming Conventions
Naming conventions play a crucial role in identifying the target of a variable. Using clear and descriptive variable names, such as `loginButton` and `resetPasswordButton`, helps Test Automation Engineers (TAEs) quickly understand which components to use.

#### Hardcoding
Hardcoding refers to embedding values directly in the code, making them difficult to change. To avoid this, use **data-driven testing**, sourcing test data from a common, easily maintainable location. While hardcoding may reduce initial development time, it is not advisable due to the potential for frequent data changes, which can be time-consuming to maintain. Instead, use constants for variables that are not expected to change often, thereby minimizing maintenance efforts.

#### Leveraging Design Patterns
Utilizing design patterns is highly recommended, as they facilitate a structured and maintainable test automation codebase when applied correctly.

#### Code Quality Tools
To ensure high-quality test automation code, it is beneficial to use **static analyzers**. Additionally, code formatters found in most IDEs can enhance the readability of the code.

#### Version Control Strategies
Beyond clean code principles, it's important to adopt a consistent branching structure and strategy in version control. Utilizing separate branches for features, releases, and defect fixes aids in understanding the contents of each branch.


### Example*: Maintaining Code Quality in Test Automation

- **Common Naming Conventions**:
  - Use meaningful names for classes, methods, and variables. For example:
    - Class: `ShoppingCart`
    - Method: `addItemToCart()`
    - Variable: `checkoutButton`
  - This enhances readability and helps TAEs quickly understand the purpose of each component.

- **Logical Project Structure**:
  - Organize the project into folders such as `/tests`, `/src`, `/data`, and `/reports`. This consistent structure aids team members in locating files easily.

- **Avoid Hardcoding**:
  - Instead of hardcoding values like product IDs, use a data-driven approach:
    ```java
    // Instead of this:
    String productId = "12345";

    // Use data-driven testing to source from a CSV file:
    String productId = testData.getProductId("Laptop");
    ```
  - This reduces maintenance overhead and allows flexibility when product details change.

- **Limit Input Parameters**:
  - Keep methods concise. For example, instead of:
    ```java
    void processOrder(String customerId, String productId, int quantity, String shippingAddress, boolean expressShipping) { ... }
    ```
    Use a dedicated Order object:
    ```java
    void processOrder(Order order) { ... }
    ```

- **Shorten Methods**:
  - Each method should perform one task. For example:
    ```java
    void verifyUserLogin() {
        // Code to input username
        // Code to input password
        // Code to click login
        // Code to check for successful login
    }
    ```
    Should be broken into smaller methods for clarity.

- **Use Logging**:
  - Implement logging at various levels (Info, Warn, Error) to facilitate debugging:
    ```java
    logger.info("Starting test for adding item to cart");
    logger.error("Failed to add item, product ID not found");
    ```

- **Leverage Design Patterns**:
  - Apply the **Page Object Model** for UI testing:
    ```java
    public class LoginPage {
        private WebDriver driver;

        public LoginPage(WebDriver driver) {
            this.driver = driver;
        }

        public void enterUsername(String username) { ... }
        public void enterPassword(String password) { ... }
        public void clickLogin() { ... }
    }
    ```
  - This creates a structured and maintainable codebase.

- **Focus on Testability**:
  - Design classes with testing in mind, allowing for easy mocking and stubbing of dependencies.

## Additional Considerations

### Naming Conventions
Using clear and descriptive variable names helps TAEs quickly identify components. For instance, `checkoutButton` is immediately recognizable compared to a generic name like `button1`.

### Hardcoding
Avoid embedding values directly in the code. Instead, use a configuration file or data-driven approach to source test data. This allows for easier updates and maintenance.

### Leveraging Design Patterns
Utilizing design patterns like the **Factory Pattern** or **Strategy Pattern** can enhance the structure and maintainability of your test automation codebase.

### Code Quality Tools
Incorporate **static analyzers** (e.g., SonarQube) and code formatters to ensure code quality and readability. This helps catch issues early in the development process.

### Version Control Strategies
Adopt a consistent branching structure in version control. For example:
- **Feature branches**: for new features
- **Release branches**: for preparing production releases
- **Bugfix branches**: for addressing defects

This strategy aids in understanding the purpose and contents of each branch, streamlining collaboration among team members.


### Example2*

### Key Principles

- **Common Naming Conventions**:
  - Use meaningful names for classes, methods, and variables. For example:
    ```python
    class ShoppingCart:
        def add_item(self, item):
            pass

    checkout_button = "checkoutButton"
    ```
  - This enhances readability and helps TAEs quickly understand the purpose of each component.

- **Logical Project Structure**:
  - Organize the project into folders such as `/tests`, `/src`, `/data`, and `/reports`. This consistent structure aids team members in locating files easily.

- **Avoid Hardcoding**:
  - Instead of hardcoding values like product IDs, use a data-driven approach:
    ```python
    # Instead of this:
    product_id = "12345"

    # Use data-driven testing:
    import pandas as pd

    test_data = pd.read_csv("test_data.csv")
    product_id = test_data.loc[0, "product_id"]  # Sourcing from a CSV file
    ```
  - This reduces maintenance overhead and allows flexibility when product details change.

- **Limit Input Parameters**:
  - Keep methods concise. For example, instead of:
    ```python
    def process_order(customer_id, product_id, quantity, shipping_address, express_shipping):
        pass
    ```
    Use a dedicated `Order` class:
    ```python
    class Order:
        def __init__(self, customer_id, product_id, quantity, shipping_address, express_shipping):
            self.customer_id = customer_id
            self.product_id = product_id
            self.quantity = quantity
            self.shipping_address = shipping_address
            self.express_shipping = express_shipping

    def process_order(order):
        pass
    ```

- **Shorten Methods**:
  - Each method should perform one task. For example:
    ```python
    def verify_user_login():
        enter_username("user")
        enter_password("password")
        click_login()
        check_login_success()
    ```
    Should be broken into smaller methods for clarity:
    ```python
    def enter_username(username):
        pass

    def enter_password(password):
        pass

    def click_login():
        pass

    def check_login_success():
        pass
    ```

- **Use Logging**:
  - Implement logging to aid in debugging:
    ```python
    import logging

    logging.basicConfig(level=logging.INFO)

    logging.info("Starting test for adding item to cart")
    logging.error("Failed to add item, product ID not found")
    ```

- **Leverage Design Patterns**:
  - Apply the **Page Object Model** for UI testing:
    ```python
    class LoginPage:
        def __init__(self, driver):
            self.driver = driver

        def enter_username(self, username):
            self.driver.find_element_by_id("username").send_keys(username)

        def enter_password(self, password):
            self.driver.find_element_by_id("password").send_keys(password)

        def click_login(self):
            self.driver.find_element_by_id("login").click()
    ```

- **Focus on Testability**:
  - Design classes with testing in mind, allowing for easy mocking and stubbing of dependencies.


## Additional Considerations

### Naming Conventions
Using clear and descriptive variable names helps TAEs quickly identify components. For instance, `checkout_button` is immediately recognizable compared to a generic name like `button1`.

### Hardcoding
Avoid embedding values directly in the code. Instead, use a configuration file or data-driven approach to source test data. This allows for easier updates and maintenance.

### Leveraging Design Patterns
Utilizing design patterns like the **Factory Pattern** or **Strategy Pattern** can enhance the structure and maintainability of your test automation codebase.

### Code Quality Tools
Incorporate **static analyzers** (e.g., Pylint) and code formatters (e.g., Black) to ensure code quality and readability. This helps catch issues early in the development process.

### Version Control Strategies
Adopt a consistent branching structure in version control. For example:
- **Feature branches**: for new features
- **Release branches**: for preparing production releases
- **Bugfix branches**: for addressing defects

This strategy aids in understanding the purpose and contents of each branch, streamlining collaboration among team members.

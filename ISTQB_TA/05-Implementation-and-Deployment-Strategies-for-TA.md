# 05: Implementation and Deployment Strategies for Test Automation – 90 minutes

## Keywords:
contract testing

## Learning Objectives for Chapter 5:
### 5.1 Integration to CI/CD Pipelines
- TAE-5.1.1 (K3) Apply test automation at different test levels within pipelines
- TAE-5.1.2 (K2) Explain configuration management for testware
- TAE-5.1.3 (K2) Explain test automation dependencies for an API infrastructure

## 5.1 Integration to CI/CD Pipelines
### 5.1.1 Apply Test Automation at Different Test Levels within Pipelines

#### Benefits of Test Automation in CI/CD Pipelines

One of the primary advantages of test automation is that tests can run unattended, making them ideal for integration into CI/CD pipelines or any automated testing pipeline that runs tests regularly. Here's how different **test levels** are typically integrated into these pipelines:

- **Configuration Tests for TAF/TAS**:
  - These tests check that the paths to the files used in the test scripts are correct, and that the files exist in the specified locations. They are considered a type of component test and are run during the build of a test automation project (TAF/TAS).

- **Component Tests**:
  - Component tests are part of the build step in a CI pipeline and are executed on individual components, such as library classes or web components. These tests serve as **quality gates** in the pipeline, ensuring that individual components meet quality standards before proceeding.

- **Component Integration Tests**:
  - If these are low-level component or SUT tests, they can be integrated into the continuous integration pipeline alongside component tests. These tests verify the interaction between different components, ensuring they function correctly together.

- **System Tests**:
  - These tests are typically part of a **continuous deployment pipeline** and act as the final quality gate before the SUT is delivered. They test the entire system to ensure it functions as expected after all components are integrated.

- **System Integration Tests**:
  - These tests check whether the separately developed system components interact as expected and are often integrated into a **continuous delivery pipeline**. They ensure that all components work together before final deployment.

Modern continuous integration systems often differentiate between the build and deployment phases of continuous delivery pipelines. In this structure, **component tests** and **component integration tests** are part of the initial build phase. Only if this phase is successful (i.e., both the build and tests pass) will the components or the SUT proceed to the deployment stage.

#### Approaches for System Integration, System, and Acceptance Testing in Pipelines

For integrating **system integration testing**, **system testing**, and **acceptance testing** into CI/CD pipelines, there are two primary approaches:

1. **Test Cases Executed as Part of the Deployment Phase**:
   - In this approach, test cases are run immediately after component deployment.
   - **Benefit**: If the tests fail, the deployment can also fail and trigger an automatic rollback, ensuring the system reverts to the last known good state.
   - **Drawback**: If tests need to be rerun, redeployment must occur first, adding time and complexity to the process.

2. **Test Cases Executed in a Separate Pipeline**:
   - Here, test cases run as part of a **separate pipeline** that is triggered after successful deployment.
   - **Benefit**: Allows for running different test suites on each deployment, which can accommodate varying test automation code. Tests do not act as a direct **quality gate**.
   - **Drawback**: Since tests are not directly tied to deployment success or failure, a manual intervention is required to roll back a failed deployment.
   - **Deployment Checks**: Simple automated test scripts can be employed to verify that the system under test (SUT) has been successfully deployed. However, these checks are basic and do not thoroughly verify functional suitability.

---

### Additional Use Cases for Pipelines in Test Automation

Pipelines can be leveraged beyond the deployment process for various test automation purposes:

- **Running Different Test Suites Periodically**:
  - For example, a **nightly regression suite** can be executed to give the team insight into the overall quality of the SUT each morning, particularly useful for longer-running test suites.

- **Running Non-Functional Tests**:
  - These tests can either be integrated into a continuous deployment pipeline or run separately to monitor non-functional quality characteristics such as **performance efficiency**. This can provide periodic assurance that the system meets performance requirements.


### 5.1.2 Explain configuration management for testware
todo

### 5.1.3 Explain test automation dependencies for an API infrastructure
todo

# **5 Test Management**
# 5.1 Test Organization
## 5.1.1 Categories of Test Techniques and Their Characteristics
Testing tasks may be done by people in a specific testing role, or by people in another role. A certain degree of **independence often makes the tester more effective** at finding defects due to differences between the author’s and the tester’s cognitive biases. Independence is not, however, a replacement for familiarity, and developers can efficiently find many defects in their own code.
- For most types of projects, it is usually best to have multiple test levels, with some of these levels handled by independent testers. 

Potential **benefits of test independence** include:
- Independent testers are likely to recognize different kinds of failures compared to developers

- An independent tester can verify, challenge, or disprove assumptions made by stakeholders
- Independent testers of a vendor can report in an upright and objective manner about the system under test without pressure of the company that hired them

Potential **drawbacks of test independence** include:
- Isolation from the development team
- Developers may lose a sense of responsibility for quality
- Independent testers may be seen as a bottleneck
- Independent testers may lack some important information

## 5.1.2 Tasks of a Test Manager and Tester
Typical test **manager tasks** may include:
- Develop or review a test policy and test strategy for the organization
- Plan the test activities by considering the context, and understanding the test objectives and risks.
- Write and update the test plan(s)

- Coordinate the test plan(s) with project managers, product owners, and others
- Share testing perspectives with other project activities, such as integration planning
- Initiate the analysis, design, implementation, and execution of tests, monitor test progress and results, and check the status of exit criteria
- Prepare and deliver test progress reports and test summary reports based on the information gathered
- Adapt planning based on test results and progress
- Support setting up the defect management system and adequate configuration management of testware
- Introduce suitable metrics for measuring test progress and evaluating the quality of the testing and the product
- Support the selection and implementation of tools to support the test process, including recommending the budget for tool selection
- Decide about the implementation of test environment(s)
- Promote and advocate the testers, the test team, and the test profession within the organization
- Develop the skills and careers of testers

Typical **tester tasks** may include:

- Review and contribute to test plans

- Analyze, review, and assess requirements, user stories and acceptance criteria, specifications, and models for testability
- Identify and document test conditions, and capture traceability between test cases, test conditions, and the test basis
- Design, set up, and verify test environment(s), often coordinating with system administration and network management
- Design and implement test cases and test procedures
- Prepare and acquire test data
- Create the detailed test execution schedule
- Execute tests, evaluate the results, and document deviations from expected results
- Use appropriate tools to facilitate the test process
- Automate tests as needed (may be supported by a developer or a test automation expert)
- Evaluate non-functional characteristics such as performance efficiency, reliability, usability,
security, compatibility, and portability
- Review tests developed by others

# 5.2 Test Planning and Estimation
A test plan outlines test activities for development and maintenance projects. Planning is influenced by the test policy and test strategy of the organization

**Test planning** activities may be:
- **Determining the scope**, objectives, and risks of testing
- Defining the **overall approach** of testing
- Integrating and coordinating the test activities into the software lifecycle activities
- Making decisions about **what to test**, the people and other resources required to perform the various test activities
- **Scheduling** of test analysis, design, implementation, execution, and evaluation activities
- **Selecting metrics for test monitoring** and control Budgeting for the test activities
- Determining the level of detail and structure for test documentation 
## 5.2.2 Test Strategy and Test Approach
- Analytical
- Model-based
- Methodical
- Process-compliant
- Directed
- Regression-averse
- Reactive

## 5.2.3 Entry Criteria and Exit Criteria (Definition of Ready and Definition of Done)

Typical **entry criteria** include the avalibility of:
- Testable requirements, user stories, and/or models
- test items that have met the exit criteria for any prior test levels
- testable requirements, user stories, and/or models
- test items that have met the exit criteria for any prior test levels

Typical **exit criteria** include:
- Planned tests have been executed
- A defined level of coverage has been achieved
- The number of unresolved defects is within an agreed limit
- The number of estimated remaining defects is sufficiently low
- The evaluated levels of reliability, performance efficiency, usability, security, and other relevant quality characteristics are sufficient

## 5.2.4 Test Execution Schedule
Ideally, test cases would be ordered to run based on their priority levels, usually by executing the test cases with the highest priority first. However, this practice may not work if the test cases have dependencies or the features being tested have dependencies. 

`priority -> dependency`

## 5.2.5 Factors Influencing the Test Effort

## 5.2.6 Test Estimation Techniques
- The metrics-based technique
- The expert-based technique
# 5.3 Test Monitoring and Control
The purpose of test monitoring is to gather information and provide feedback and visibility about test activities. Information to be monitored may be collected manually or automatically and should be used to assess test progress and to measure whether the test exit criteria.
## 5.3.1 Metrics Used in Testing
Metrics can be collected during and at the end of test activities in order to assess:
- Progress against the planned schedule and budget
- Current quality of the test object
- Adequacy of the test approach
- Effectiveness of the test activities with respect to the objectives 

**Common test metrics** include:
- Percentage of planned work done in test case preparation 

- Percentage of planned work done in test environment preparation
- Test case execution
- Defect information
- Test coverage of requirements, user stories, acceptance criteria, risks, or code
- Task completion, resource allocation and usage, and effort
- Cost of testing, including the cost compared to the benefit of finding the next defect or the cost compared to the benefit of running the next test

## 5.3.2 Purposes, Contents, and Audiences for Test Reports
The purpose of test reporting is to summarize and communicate test activity information, both during and at the end of a test activity

This chapter is weird :) 
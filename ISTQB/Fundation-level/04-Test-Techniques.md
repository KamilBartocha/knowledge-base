# **4 Test Techniques**
# 4.1 Categoties of Test Techniques
The purpose of a test technique, including those discussed in this section, is to help
in identifying test conditions, test cases, and test data.

## 4.1.1 Categories of Test Techniques and Their Characteristics

- **Black-box** are based on an analysis of the appropriate test basis (formal requirements documents, specifications etc.) Concentrate on the inputs and outputs of the test object without reference to its internal structure.

- **White-box** are based on an analysis of the architecture, detailed design, internal structure, or the code of the test object. Concentrate on the structure and processing within the test object.

- **Experience-based** leverage the experience of developers, testers and users to design, implement, and execute tests. These techniques are often combined with black-box and white-box test techniques.

# 4.2 Black-box Techniques
## 4.2.1 Equivalence Partitioning
Equivalence partitioning divides data into partitions (equivalence classes) in such a way that all the members of a given partition are expected to be processed in the same way.

There are equivalence partitions for both valid and invalid values.
### Properties:
- **Valid values** are values that should be accepted by the component or system. An equivalence partition containing valid values is called a “valid equivalence partition.”
- **Invalid values** are values that should be rejected by the component or system. An equivalence partition containing invalid values is called an “invalid equivalence partition.”
- Partitions can be identified **for any data element** related to the test object.
- Any partition may be divided into sub partitions if required.
- **Each value must belong to one and only one** equivalence partition.
- When **invalid** equivalence partitions are used in test cases, they should be **tested individually**.

### Coverage
- To achieve 100% coverage with this technique, test cases must cover all identified partitions (including invalid partitions) by using a minimum of one value from each partition.

- Coverage is measured as the number of equivalence partitions tested by at least one value, divided by the total number of identified equivalence partitions, normally expressed as a percentage.

- Equivalence partitioning is applicable at all test levels.

### Example:
!!! TODO !!!
## 4.2.2 Boundary Value Analysis
- Boundary value analysis (BVA) is an extension of equivalence partitioning, but can only be used when the partition is ordered, consisting of numeric or sequential data.

- The **minimum and maximum values** of a partition are its boundary values

- Boundary value analysis can be applied at all test levels. This technique is generally used to test requirements that call for a range of numbers.
### Coverage
Boundary coverage for a partition is measured as the number of boundary values tested, divided by the total number of identified boundary test values, normally expressed as a percentage.

### Example:
!!! TODO !!!
## 4.2.3 Decision Table Testing 
**Decision tables** are a good way to record complex business rules that a system must implement. When creating decision tables, the tester identifies conditions (often inputs) and the resulting actions (often outputs) of the system. These form the rows of the table.

- **Each column corresponds to a decision rule** that defines a unique combination of conditions which results in the execution of the actions associated with that rule. The values of the conditions and actions are usually shown as Boolean values.

- A **full decision table** has enough columns (test cases) to cover every combination of conditions.

### Coverage:
The common minimum coverage standard for decision table testing is to have at least **one test case per decision rule** in the table.
This typically involves covering all combinations of conditions.

- **Coverage is measured** as the number of decision rules tested by at least one test case, divided by the total number of decision rules, normally expressed as a percentage.

- The strength is that it helps to identify all the important combinations of conditions, some of which might otherwise be overlooked. It also helps in finding any gaps in the requirements.

### Example:

## 4.2.4 State Transition Testing
Components or systems may respond differently to an event depending on current conditions or previous history. 

- The previous history can be summarized using the concept of states. A state transition diagram **shows the possible software states**, as well as how the software enters, exits, and transitions between states.

- A state transition table shows all valid transitions and potentially invalid transitions between states.

- Tests can be designed to cover a typical sequence of states, to exercise all states, to exercise every transition, to exercise specific sequences of transitions, or to test invalid transitions.

- State transition testing is used for menu-based applications and is widely used within the embedded software industry.
### Coverage
**Coverage is commonly measured** as the number of identified states or transitions tested, divided by the total number of identified states or transitions in the test object, normally expressed as a percentage.

### Example:
!!! TODO  !!!
## 4.2.5 Use Case Testing
Tests can be derived from use cases, which are a s**pecific way of designing interactions with software items**. Use cases are associated with actors (human users, external hardware, or other components or systems) and subjects (the component or system to which the use case is applied).

- Each use case **specifies some behavior** that a subject can perform in collaboration with one or more actors. A use case can be described by interactions and activities, as well as preconditions, postconditions.

- A use case Tests are designed to exercise the defined behaviors (basic, exceptional or alternative, and error handling).
### Coverage:
Coverage can be measured by the number of use case behaviors tested divided by the total number of use case behaviors, normally expressed as a percentage.
### Example:
!!! TODO !!!

# 4.3 White-box Test Techniques
White-box testing is b**ased on the internal structure** of the test object. White-box test techniques can be used at all test levels, but the two code-related techniques discussed in this section are most commonly used at the component test level.

### Code Realated Techniques are:
- **Statement Testing** (potential executable statements in the code)
- **Decision Testing** (decisions in the code and tests the code that is executed based on the decision outcomes).
**for an IF statement**, one for the true outcome and one for the false outcome.

Achieving 100% decision coverage guarantees 100% statement coverage (but not vice versa).

# 4.4 Experience-based Test Techniques
Test cases are derived from the **tester’s skill and intuition, and their experience**. These techniques can be helpful in identifying tests that were not easily identified by other more systematic techniques.

- Coverage can be difficult to assess and may not be measurable with these techniques.

## 4.4.1 Error Guessing
Error guessing is a technique used to anticipate the occurrence of errors, defects, and failures, based on the tester’s knowledge, including:
- How the application has worked in the past
- What kind of errors tend to be made
- Failures that have occurred in other applications
- A methodical approach to the error guessing technique is to **create a list of possible errors**, defects, and failures, and design tests that will expose them.

## 4.4.2 Exploratory Testing
In exploratory testing Tests are designed, executed, logged, and **evaluated dynamically during test execution**.

- The test results are used to learn more about the component or system, and to create tests for the areas that may need more testing.
- Exploratory testing is most useful when there are few or inadequate specifications or significant time pressure on testing. 
- Exploratory testing is strongly associated with reactive test strategies. 
- Exploratory testing can incorporate the use of other black-box, white-box, and experience-based techniques.

## 4.4.3 Checklist-based Testing

In checklist-based testing, testers design, implement, and execute tests to cover test conditions found in a checklist. 

- As part of analysis, testers create a new checklist or expand an existing checklist, but testers may also use an existing checklist without modification. 
- Such checklists can be built based on experience, knowledge about what is important for the user, or an understanding of why and how software fails.
- Checklists can be created to support various test types, including functional and non-functional testing.
# Unit testing and Mocking

- Explain what makes a test a unit test.
 - test

- Explain properties that make a unit test a good unit test


- Provide examples (in words, not code) of JUnit tests which are not Unit tests


- What is meant by a test fixture?


- Explain, using a short example, the rationale behind the Arrange - Act - Assert strategy for testing


- Explain the topics: State Verification vs Behaviour Verification and strategies for testing each


- Explain about the JUnit Framework, how to include it in a project, and how to write tests


- Explain a few rules of what makes a good Unit test, and rules for what makes code testable (or untestable). 


- Explain about the SOLID rules plus a number of the additional rules given in Effective Unit Testing focusing on WHY following these rules makes code more testable


- Explain the topic “data driven testing” and ways to do it, using both “plain” JUnit and alternative libraries which easily lets you read test data from files (cvs, Excel etc.)
- How, or if, tools like jacoco or similar can be used to measure the "quality" of our tests


- Explain strategies/frameworks used to unit test single classes with dependencies


- Explain about Test Doubles and specific types like: Dummy Objects, Test Stubs, Mock Objects and their purpose for Unit testing objects with dependencies.


- Explain the difference between state based testing versus behaviour based testing, and provide practical examples using JUnit and a relevant Mock-framework.


- Explain about the development process TDD in general, and the steps involved when using this process.


- Why would you consider alternative matchers like for example Hamcrest matchers in a JUnit project? Provide examples to demonstrate, how to set up a project to use Hamcrest, - the effect of using Hamcrest matchers compared to JUnit's basic Asserts.


- Explain why testers just love the Dependency Injection Pattern


- Explain about a typical suggested Project layout for a Java/JUnit based project (for example the one you get with a typical maven project) and the benefits gained from such a layout

---
 
**Explain using examples you have provided, how to unit-test**

- A method with no return value
- A dependency method with required inputs and no return value
- Exceptional behaviour
- A Single method, with multiple input values (and corresponding expected results)
- A test with dependencies of other classes


- Explain using an example how to do Data Driven Unit testing (read data from external sources)


- Explain basically about the architecture in JUnit 5.X, how to set up a project for JUnit 5.X testing and provide a few examples to demonstrate some of the new features.


- Demonstrate, preferably using a real life example, ways to handle many input values, and expected values


- Explain how to setup a Java Project to use JUnit and Mockito and provide examples, using exercises given throughout the semester, for how to use the framework.


- The textbook "JUnit in action" list a number of best practices for how to write testable code. Explain a number of these (feel free to include other), providing code examples to support your arguments.

--- 

**_Demonstrate your solution to the study point exercise "Unit testing"._**

You should (as a minimum):

- Explain how you have set up your test cases with JUnit and how your test cases are executed
- Execute your test cases
- List the different JUnit asserts that exist and which you have used
- Account for the need for JUnit test parameters and test factories in your test cases
- Demonstrate how you have tested for exceptions

---

**_Demonstrate your solution to the study point exercise  "UNIT Testing, Testable Code, Mocking and Code Coverage"._**

You should (as a minimum):

- Explain the necessary steps you did to make the code testable, and some of the patterns involved in this step
- Execute your test cases
- Explain basically about JUnit, Hamcrest, Mockito and Jacoco, and what problems they solve for testers
- Demonstrate how you used Mockito to mock away external Dependencies
- Demonstrate how/where you did state-based testing and how/where you did behaviour based testing
- Explain about Coverage Criterias, using the results presented by running jacoco (or a similar tool) against you final test code.
- Explain/demonstrate what was required to make this project use, JUnit (Hamcrest), Mockito and jacoco

---

**_Demonstrate your solution to the study point exercise "Testing Real Life Code"._**

You should (as a minimum):

- Explain the purpose of the Test (what the previous test exposed, and what your test expose)
- Explain about Parameterized Tests in JUnit and how you have used it in this exercise.
- Explain the topic Data Driven Testing, and why it often makes a lot of sense to read test-data from a file
- Your answers to the question; whether what you implemented was a Unit Test or a JUnit Test, the problems you might have discovered with the test and, your suggestions for - ways this could have been fixed.
- The steps you took to include Hamcrest matchers in the project, and the difference they made for the test

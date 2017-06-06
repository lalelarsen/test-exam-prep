# Unit testing and Mocking

- Explain what makes a test a unit test.
  - hvis en test tester en specifik del af koden, eller et specifikt unit, så kan det kaldes en unit test. et unit kan være alt lige fra en funktion til en hel klasse. testen afgøre hvorvidt at det specifikke unit gør hvad det skal, f.eks. at det returnere det rigtige.

- Explain properties that make a unit test a good unit test
  - en unit test skal være hurtig. langsome tests har man ikke lyst til at køre.
  - nem at skrive = nem at læse. man skal nemt kunne læse og forstå intentionen med testen.
  - ikke være afhængig af andre tests og andre ting. skal kunne køre enkeltvis.
  - må ikke ændre ekstern data. 
  - skal kun teste en ting/en feature.

- Provide examples (in words, not code) of JUnit tests which are not Unit tests
  - en integrations test. en integrations test kan nemt skrives i JUnit, men modsat en unit test. så tester integration flere units, da den fokusere på samarbejde mellem units.
  - Frontend testing kan også blive skrevet med JUnit, via frameworket Selenium.

- What is meant by a test fixture?
  - hvis en test er afhængig af noget der kan ændre sig, kan man udnytte en test fixture. et test fixture kan f.eks. være at loade sin database med kendte parameter, og derved opfylde preconditions for testen.

- Explain, using a short example, the rationale behind the Arrange - Act - Assert strategy for testing
  - arrange, kunne være en test fixture. preconditions met.
  - act, selve testen. det kunne være kaldet af en metode som vi ville teste. gør arbejde.
  - assert, tjek om vores outcome passer med det vi forventet. 
  - et eksempel kunne være:
    - arrange: input kendte parameter i databasen
    - act: hent alle persone med alderen over 18
    - assert: tjek om det passer med det vi forventet.

- Explain the topics: State Verification vs Behaviour Verification and strategies for testing each
  - state verification, er hvor man teste at et givent objekt og dets collaborators(noget objectet er afhængig af. f.eks. en andens klasse) er i det forventet stadige. det kunne være at der er blevet tilføjet et objekt til en liste, og den derfor er blevet 1 større.
  - behaviour verification, er hvor man sikre sig at de rette metoder er blevet kaldt med de rette parameter. det kan man gøre ved hjælp af f.eks. mocks. ved at mocke et object væk kan vi tjekke hvorvidt en metode er blevet kaldt osv.

- Explain about the JUnit Framework, how to include it in a project, and how to write tests
  - JUnit er et framework til java, som skal gøre det nemmere at skrive tests. JUnit udnytter sig af nogle tags, som definere elementer i koden. f.eks. definere man en test via @Test -tagget. man inkludere JUnit, via en jar file som man kan implementere selv, eller via en dependency i Maven

- Explain a few rules of what makes a good Unit test, and rules for what makes code testable (or untestable). 
  - læs det første spørgsmål for at se hvad der gør en unit test god.
  - 

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

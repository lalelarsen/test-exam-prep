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
  - Hvilken slags kode er nemt testable:
    - Hvis det følger SOLID reglerne
    - hvis det har få dependencies
    - hvis det følger Single responsibility princippet
    - hvis det udnytter sig af injections
    - hvis det undgår static metoder og singleton
    - Favour Composition over Inheritance
    - Favour Polymorphism over Conditionals

- Explain about the SOLID rules plus a number of the additional rules given in Effective Unit Testing focusing on WHY following these rules makes code more testable
  - Solid
    - S, Single responsibility: et unit skal kun have et ansvar, fordi hvis det ikke har, så bliver testen til den givende metode rigtig kompliceret
    - O, Open/closed: en metode skal være åben til extension men ikke modifications. fordi extentions ikke burde lave fejl på existerende test, hvor en modification derimod godt kan.
    - L, Liskov substitution principle: et child object burde kunne erstatte sin parent object. hvis vi har et objekt som udnytter en metode som er afhængig af noget andet, så er det vigtigt at det den er afhængig skal kunne erstattes med et child f.eks. fordi hvis den ikke kan, så laver den noget arbejder som gør det specifikt. og derfor kan det den er afhængig af ikke bare mockes væk.
    - I, interface segration principle: ??
    - D, Dependency inversion principle: et objekt burde kun vide hvad et object gør, ikke hvad den er. med andre ord. den burde kun kende til interfaces af objekter. for det gør det nemmere at mocke væk.
  - Se mere i det overstående spørgsmål.


- Explain the topic “data driven testing” and ways to do it, using both “plain” JUnit and alternative libraries which easily lets you read test data from files (cvs, Excel etc.)
  - data driven testing kan åbnes med ren JUnit via det der kaldes Paramatised tests. hvor i man angiver en række parameterer (det data man ville teste på) og så køre testen lige så mange gange som der er parameterer.
  - en anden måde kan være ved at læse det fra en csv fil(Comma seperated file). strukturen er lidt det samme som det man laver i en paramatized test. men fordelen ved at få det fra en fil er at man kan have andre folk som ikke ved noget om programmering til at lave den. det kan gøres med et libary fra JUnit der hedder JUnitParamsRunner
  
- How, or if, tools like jacoco or similar can be used to measure the "quality" of our tests
  - de kigger på line coverage. det ville sige om vores test kommer hele vejen rundt, og tester alt i metoden. det samme gælder for hele klasser. altså om alle linjer i en klasse er blevet testet og derved alle metoder i klassen. et eksempel på en metode som er blevet testet hvor alle linjer ikke er testet, kunne f.eks. være en metode med en if statement. hvis vores test kun teste hvor if statementet modtager en true, har vi aldrig rørt ved false conditionen, og derfor ikke været hele metoden igennem. det vise værktøjet jacoco os. den fortæller os i % hvor meget af en klasse vi har testet. og derfor giver den os en idé om hvor meget af klassen er testet procent mæssigt.

- Explain strategies/frameworks used to unit test single classes with dependencies
  - Mockito er et framework som hjælpe med at lave unit test på metoder der er afhængig af andre ting. hvis vi laver en test som tjekker hele metoden og alle den afhængigheder er det ikke længere en unit test men en integrations test. derfor bruger vi frameworks som mockito til at mocke de dependencies væk. vi kan ved hjælp af mockito sikre os at afhængighederne ikke lave fejl ved at bestemme hvad de skal gøre og returnere så vi er i fuld kontrol.

- Explain about Test Doubles and specific types like: Dummy Objects, Test Stubs, Mock Objects and their purpose for Unit testing objects with dependencies.
  - Dummy objects: et objekt der bliver smidt rundt, men aldrig brugt. ingen af dens metoder i brug. oftes brugt bare for at fylde en parameter.
  - stub: en stub er bare til for at returner en specifik ting. den gør ikke noget arbejde ud over det den skal returnere i den givende test.
  - mock: et objekt der er preprogrammed med en forventing. et slags plan om hvad der kommer til at ske, eller hvad der skal ske når den får et specifikt input vi har fortalt den.
  - fake objects: et object med rigtig kode, men som oftes skyder genvej, den kan ikke bruges i den rigtige kode, men den kan f.eks. gøre et meget langt loop kort ved at skyde genvej.
  - spies: er det samme som en stub, men den gemmer information udfra hvordan den blev kaldt. eller hvor mange gange den blev kaldt osv.


- Explain the difference between state based testing versus behaviour based testing, and provide practical examples using JUnit and a relevant Mock-framework.
  - læs det tidligere spørgsmål angående hvad state og behaviour based testing er.
  - et eksempel på behaviour based kunne være mockitos when: when(object.method(anyInput())).thenReturn("Hello World")
  - et eksempel på state based kunne være: variable v = object.method(input); Assert(v, "Hello World")


- Explain about the development process TDD in general, and the steps involved when using this process.
  - tdd cycle: add test, see test fail, write code, run test, refractor. repeat.
  - test driven development, er idéen om at vide hvordan koden skal fungere før den overhoved er skrevet, derfor sikre vi os at koden gør hvad den skal kunne ved at kunne køre en test som allerede eksistere før vi har lavet koden. man kan derfor nemt se hvornår man er færdig med koden.


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

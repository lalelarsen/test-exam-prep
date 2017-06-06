# Testing throughout the software life cycle

[Software Development Life Cycle (SDLC) phases](http://istqbexamcertification.com/what-are-the-software-development-life-cycle-sdlc-phases/)

- Explain the characteristics of good testing that are applicable to any life cycle model

---

- Explain the major objectives of the different test levels: unit test, integration test, system test and acceptance test

	- **Unit testing:** Unit tests er den mindste testbare del af en applikation som fx funktioner, klasser, metoder og interfaces. 
		* Formålet med unit tests er, at sikre at koden opfylder design og krav, og fungerer som forventet. Så en unit test er, at dele programmet op i mange små dele, og at teste at hver lille del fungerer korrekt. 
		* Unit testing udføres af udviklerne. 
		* Bliver udført inden integrationstest. 
		* White Box Testing bruges til at udføre testene. 
		* Læs mere om unit testing [her](http://istqbexamcertification.com/what-is-unit-testing/)
	- **Integration testing:** tester integrationen eller interfaces mellem komponenter, interaktioner mellem forskellige dele af systemet som fx operativ system, fil system og hardware, eller interfaces mellem systemet. 
		* Formålet er, at sikre at koblingen mellem forskellige komponenter af systemet fungerer som forventet. 
		* Integration tests bliver udført efter to komponenter er blevet integreret. Som det vises på billedet nedenfor når de to forskellige komponenter "Module A" og "Module B" er integreret, så bliver integrations test udført. 
		* ![What is integration testing](/week-2/What-is-IntegrationTesting.jpg)
		* Læs mere omg integration test og de forskellige teknikker [her](http://istqbexamcertification.com/what-is-integration-testing/) (der er en del forskellige teknikker til integrations test, så det er en god idé lige at læse det)
	- **System testing:** her tester man hele systemets samlede funktionalitet. 
		* Dette kan inkludere tests baseret på risks og/eller kravspecifikation, forretningsprocesser, use cases, system resourcer. 
		* System tests er ofte den endelig test for, at bekræfte at systemet lever op til specifikationerne og dets formål. 
		* System tests foretages af "specialists testers" eller "uafhængige testere". 
		* System tests tester både funktionelle og ikke-funktionelle krav. 
		* Læs mere om system testing [her](http://istqbexamcertification.com/what-is-system-testing/)
	- **Acceptance testing:** Når systemet har fået rettet alle eller de fleste fejl, vil det bliver afleveret til brugeren eller kunden til **Acceptance test** eller **User Acceptance Test (UAT)**. 
		* Acceptance test bliver primært udført af brugeren eller kunden, selvom der kan være andre interessenter også kan være involveret. 
		* Målet med acceptance test er, at etablere tillid til systemet. 
		* Der er flere forskellige typer acceptance test: 
			1. **User acceptance test:** fokuserer primært på systemets funktionalitet. Udføres af brugerne og "application managers". 
			2. **Operational acceptance test:** Validerer om systemet lever op til kravene til, at kunne fungere. I de fleste virksomhederne bliver disse udført af system adminstratoren inden systemet bliver released. Disse test inkluderer ofte test af backup/gendannelse, vedligeholdelses opgaver og periodiske tjek af sikkerhedshuller. 
			3. **Contract acceptance test:** 
			4. **Compliance acceptance test:**
		* Fokus på krav og kunden. 
		* Læs mere om acceptance test [her](http://istqbexamcertification.com/what-is-acceptance-testing/)

---

- Explain the 4 test types: functional testing, non-functional testing, structural testing and change related testing

	1. **Functional testing:** man tester funktionerne af "component"- eller "system" testene. Det referer til handlinger eller aktiviterer, som referer til en bestemt handling eller funktion af koden. Funktionelle test har en tendens til, at verficiere om "kan brugeren gøre dette?" eller "virker denne specifikke feature?"
		* Foretages på alle niveauer. 
	2. **Non-functional testing:** Kvaliteten af systemet testes. Referer til aspekter af systemet, som ikke er direkte relateret til en specifik funktion eller bruger handling, som scailibity eller sikkerhed. Fx hvor mange brugere kan logge ind samtidig? ikke-functional tests bliver udført på alle niveauer, ligesom funktionelle test. 
		* Performance test.
		* Load testing (scalability)
		* Stress testing.
		* Usability testing. 
		* Maintainability testing.
		* Reliability testing (robustness)
		* Portability testing. 
		* Læs mere om ikke-funktionelle tests [her](http://istqbexamcertification.com/what-is-non-functional-testing-testing-of-software-product-characteristics/)
	3. **Structural testing:** Strukturen af systemet eller komponenten testes. Ofte refereret til som "white box" testing - interesserede i, hvad der sker "inden i applikationen". 
		* Nødvendigt for testerne, at have kendskab til de interne implementationer i koden. 
	4. **Change related testing:**

---

- Identify and describe relevant non-functional tests from one of your exercises during the course

The [system testing exercise with jmeter](https://github.com/hilleer/system-testing-study-point) - benytter jMeter til at requeste vores backend, og verifcere resultatet af forskellige inputs. 

Resultaterne af, at kalde vores backend med varirende værdier, som var `newCustomer`, `loyaltyCard` og `coupon` - kombinationen af disse, skulle returnere en varierende discount. 

Vores resultater for henholdsvis 10, 100 og 1000 brugere med en ramp up time på 10 sekunder. 

![](/week-1/getAllCustomers-10.png)
![](/week-1/getAllCustomers-100.png)
![](/week-1/getAllCustomers-1000.png)

Vores jmeter struktur:

![](/week-1/jmeter-setup.png)

**[backend til opgaven](https://github.com/hilleer/banking-backend)**

[Opgave beskrivelse](https://github.com/cnls/PBA_Test/blob/master/SystemTesting/SystemTestingStudyPointExercises.pdf)

---

- Describe the purpose of regression testing

Når man ændrer i en applikationskode, kan det medføre uforudsete problemer. Derfor er det vigtigt, sammen med de nye ændringer, at teste den eksisterende funktionalitet. Dette bruges regression testing til. 

Formålet er altså, at finde de bugs som måtte blive skabt ved et uheld, når man tilføjer nye ændringer og modifikationer. 

Når man regressionstester prioriterer man sine test cases således, at afhænger af de ændringer der er lavet til en feature eller et modul i applikationen. Hele den feature eller det modul hvor ændringer eller modifikationen er lavet, bliver prioriteret til testene. 

---

- Compare maintenance testing (testing an existing system) to testing a new application with respect to test types, triggers for testing and amount of testing.

**OBS Tilføj ydereligere!!**

---

- Explain the V-model:

![figure-2-2-v-model image illustration](/week-1/figure-2-2-v-model.png)

Betyder "Verification and validation model".

Den v-formede livscyklus er en illustration af en sekventiel eksekveringsprocess. Hver fase skal fuldføres, før den næste kan begynde. De forskellige faser består af:

**Requirements:** BRS og SRS. "System test" plan laves. Test planen fokuserer på, at opfylde funktionaliteten som er specificeret i kravspecifikationen. 

**High level design:** der er fokus på systemets arkitektur og design. Det giver et billede af løsningen, platformen, systemet og produktet. Der laves en plan for integration test, for at teste samarbejdet mellem systemets forskellige moduler og deres evne til at fungere sammen. 

**Low level design:** Software komponenterne bliver designet. Den faktiske logik defineres for alle systemets komponenter. Klasse diagram med alle metoder og relationer mellem klasser. Component tests laves. 

**Implementation:** Alt kodningen. Når kodningen er færdig, fortsætter eksekveringen op af den højre side af V-modellen, hvor de testene der tidligere er udviklet bliver benyttet.

**Coding:** Bunden af V-modellen. Modul designet bliver konverteret til brugbart kode af udviklerne, og der skrives og køres unit test på denne. 


---

- Describe tools which can support test activities at the various test levels in the V-model. You may demonstrate one or more tools.

**OBS Tilføj ydereligere!!**

---

- Describe test roles and test organization in a V-model system development project.

V-modellen deler systemet op og organiserer i fire forskellige test roller/kategorier - system-, integration-, component- og unit tests. 

Formålet for dem hver især varrierer, og V-modellens funktion afhænger af deres tilstedeværelse. 

**OBS Tilføj ydereligere!!**

---

- Describe strengths and weaknesses of the V-model. What are the alternatives?

**Fordelene** ved V-modellen er, at den er simpel og nem at bruge. Der laves test planer og design laves inden koden, hvilket har til formål at spare tid. 
Fejl bliver fundet i et tidligt stadie. 
Fungerer godt med mindre projekter, hvor kravspecifikationen er nemt at forstå og overskue. 

**Ulemperne** ved V-modellen er, at den er meget "stiv" og ikke særlig fleksibel. 
Softwaren bliver udviklet i implementations fasen, så der er ingen tidlige prototyper. 
Hvis man foretager ændringer midtvejs, bliver man nødt til at opdatere test dokumenterne. 

**Alternativerne** er vandfaldsmodellen, den incrementelle model, den iterative model, spiral modellen. 

---


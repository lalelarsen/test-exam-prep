# Fundamentals of testing

Nyttigt link: [https://www.quora.com/Why-software-testing-is-important](https://www.quora.com/Why-software-testing-is-important)

- Explain why testing is necessary by giving examples

	* Generelt:

		* Software testing er nødvendigt, fordi vi alle begår fejl. Nogle fejl vil være ligegyldige og uden betydning, men andre vil være dyre, betydelige og have indflydelse på vores system(er). Så at teste er med til at opdage, når vi laver fejl i koden, da vi antager, at vi altid vil lave fejl. 
		* Tests kan være med til, at reducere omkostninger da testene er med til, at udvikle dokumentationen for systemet. Derudover kan de også sikre kvaliteten af produktet.
		* De gør det nemmere at vedligeholde produktet/systemet. Hvis vi ødelægger noget når vi retter i koden, skal testene være konstrueret således, at de fanger den nyligt opståede bug. 
		* Det påviser kvaliteten af produktet &rarr; testene fejler ikke, altså ingen fejl (HUSK: et system er aldrig helt fejlfrit) og dette hjælper med, at arbejde med inkremental udvikling. 

	* Eksempler:

		1. **Banking software:** 
			* Overførsel fra bank A til bank B - det bank B modtager ikke det korrekte beløb eller der bliver tilskrevet et forkert gebyr. 
			* Korrekte kunde som logger ind på sin netbank. 
			* Sikkerhedsmæssige test, således at kundernes idenditet/data ikke bliver exposed. 
		2. **Flight booking service:** 
			* Flere kunder booker samme sæde, hvad sker der så? 
			* Hvad hvis der er udsolgt?

- Explain the difference in meaning between the root cause of a defect and its effects



- Explain the common objectives of testing

	* At finde bugs/fejl som skabes når man udvikler/viderbygger systemet (**continous integration** &rarr; "gateway" før man deploy til produktion). 
	* At kvalitetssikre produktet, og at påvise dette (kvaliteten af produktet)
	* Undgå bugs/fejl. 
	* At sikre, at slutresultatet lever op til kravspecifikationen. 
	* Testene fremviser, at systemet virker. 
	* Lave dokumentation. 
	* Reducere omkostninger &rarr; omkostningerne for, at finde og rette fejl øges over tid, så det er vigtigt, at finde dem så tidligt som muligt. 

- Provide examples for the objectives of testing in different phases of the software life cycle

- Explain the difference between testing and debugging

Når man benytter automatiserede tests er formålet mere, at opdage fejlene således, at man rent faktisk kan rette dem. 

Debugging går ud på, at undersøge og rette, hvorfor den og den test fejler - altså rette årsagen i koden til, at netop den test fejler. 

- Explain some of the seven principles of testing

	* The seven principles:
		1. Testing shows presence of defects. Test er med til at påvise, at der er fejl i systemet, men kan ikke konkret bevise, at der ikke er fejl overhovedet. Dvs., at selv efter at have testet et system, kan vi ikke bevise/garantere at systemet er 100% fejlfrit. 
		2. Exhaustive testing is impossible. Det er umuligt at teste alt i et softwaresystem, hvor alle fx kombinationer af inputs er inkluderet. Så i stedet for, at lave fuldstændige test af systemet, laver man "risks" og "priorities". Dvs. man vurderer hvor der er størst risiko for, at der kunne være bugs, og prioriterer udfra dette. 
		3. Early testing. Testene bør skrives så tidligt som muligt, i udviklingen af systemet, så man løbende tester softwaren når der tilføjes features til systemet - herved er der større sandsynlighed for, at man opdager bugs når de opstår. 
		4. Defect clustering.
		5. Pesticide paradox. Hvis den samme type test bliver gentaget igen og igen og igen, vil de samme test cases ikke længere finde nye bugs. For at undgå dette, er det enormt vigtigt ofte at revurdere og optimere sine test cases, og også tilføje nye test som tester andre dele af systemet for potentielt, at finde flere fejl. 
		6. Testing is context dependent. 
		7. Absence – of – errors fallacy
	* Læs om de syv principer [her](http://istqbexamcertification.com/what-are-the-principles-of-testing/)

---
title: "Powrót do Springa – refleksje po przerobieniu pierwszych 14 lekcji kursu Master Spring Boot"
date: 2025-07-07
lang: pl
slug: spring-framework-powrot-lekcje-1-14
category: blog-entry
---

Po kilku miesiącach przerwy wracam do nauki z kursem [**Master Spring Boot 3 & Spring Framework 6 with Java**](https://www.udemy.com/course/spring-boot-tutorial-for-beginners/) od in28minutes. Kurs został w międzyczasie zaktualizowany — **ostatnia wersja pochodzi z kwietnia 2025**, a wraz z nią pojawiło się wiele nowych lekcji, rozbudowane wprowadzenie i lepsza struktura.

Przerobiłem od nowa sekcje 1–3 (lekcje 1–14), które pełnią rolę **wprowadzenia do ekosystemu Springa oraz solidnego ugruntowania podstaw programowania obiektowego i zależności między klasami**. Było to dla mnie nie tylko przypomnienie, ale też doskonała okazja do stworzenia **własnych rozszerzeń dydaktycznych i repozytorium edukacyjnego**.

## 📚 Co udało mi się stworzyć na podstawie tych lekcji?

### ✅ Notatki lekcja po lekcji  
Zamiast kopiować treść kursu, przygotowałem własne **skondensowane podsumowania** z każdej lekcji, m.in.:
- czym są `IoC`, `DI`, `Spring Beans`,
- czym różni się **tight coupling** od **loose coupling**,
- jak wygląda pierwsze uruchomienie aplikacji bez Spring Boot.

🔗 Repozytorium: [learn-spring-framework](https://github.com/programista1024/learn-spring-framework)

### 🧠 Słowniczek pojęć  
Powstał także **słownik terminów z lekcji 1–14**, który zebrałem na jednej stronie, aby uporządkować pojęcia używane w kursie i własnym kodzie. Będzie też świetną bazą do quizów i fiszek powtórkowych.

### 🎮 Mini-projekt: Gra w Javie  
Zrealizowałem w pełni **projekt edukacyjny „GameRunner”** – najpierw w wersji z silnym sprzężeniem, a potem przygotowując podłoże do przejścia na Springa i interfejsy.

### 🧩 Zadania praktyczne  
Na podstawie lekcji stworzyłem zestaw **zadań dla uczniów** – od wersji podstawowej po rozszerzoną, z dodatkowymi scenariuszami i refaktoryzacją:
- zmiana domeny (np. z gier na pilot i urządzenia RTV),
- dodanie poziomu trudności gry,
- obsługa wyjątków.

## 🔍 Własne pogłębianie tematu: coupling i historia inżynierii oprogramowania

Jednym z tematów, który szczególnie mnie zaciekawił na tym etapie kursu, był **problem tight vs loose coupling** – czyli stopień powiązania między klasami w aplikacji.

Z pozoru może się wydawać, że to jedynie techniczny detal, ale zagadnienie to ma **głębokie konsekwencje projektowe**, a jego źródła sięgają **lat 70-tych XX wieku**!

W ramach własnych poszukiwań trafiłem m.in. na klasyczną publikację:  
📄 *Reliable Software Through Composite Design* autorstwa **Glenforda J. Myersa** (1975),  
która już wtedy podkreślała znaczenie modularności, kompozycji i rozdzielania odpowiedzialności pomiędzy komponentami.

To pokazuje, że chociaż technologia się zmienia, **fundamenty inżynierii oprogramowania pozostają aktualne** – a Spring Framework (i cały ekosystem) świetnie się wpisuje w te idee, dostarczając konkretne narzędzia do ich realizacji (DI, IoC, komponenty, serwisy).

## 🎯 Cel na kolejne tygodnie

W kolejnych wpisach planuję:
- przejście do **interfejsów i anotacji Springa**,
- wdrażanie pierwszych komponentów z wykorzystaniem Spring Container,
- dalszy rozwój materiałów pomocniczych: quizów, projektów i diagramów.

## 🙋‍♂️ Dla kogo są te materiały?

Ten kurs to świetna baza nie tylko dla samodzielnych uczniów Springa, ale też:
- dla nauczycieli szukających scenariuszy lekcji i ćwiczeń,
- dla studentów szukających projektów na zaliczenie,
- dla programistów backendowych wracających po przerwie do Javy i Springa.

🧾 Wszystkie notatki, projekty i materiały dydaktyczne będę umieszczał sukcesywnie na:  
🔗 [https://github.com/programista1024/learn-spring-framework](https://github.com/programista1024/learn-spring-framework)  
oraz omawiał na blogu:  
🔗 [https://programista1024.pl](https://programista1024.pl)

🎓 Zachęcam do śledzenia repozytorium, eksperymentowania z kodem i tworzenia własnych wariantów projektów. Spring to ogromny ekosystem, ale jak pokazują pierwsze lekcje – wszystko zaczyna się od dobrego zrozumienia podstaw.

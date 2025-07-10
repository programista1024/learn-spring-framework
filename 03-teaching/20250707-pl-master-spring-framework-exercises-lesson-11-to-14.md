<!--
📄 Opis pliku:
Ten plik zawiera zestaw zadań praktycznych opartych na lekcjach 11–14 kursu "Master Spring Boot 3 & Spring Framework 6 with Java" (Udemy, autor: in28minutes).
Zadania przeznaczone są dla osób początkujących, uczących się Spring Framework, oraz dla nauczycieli/mentorów szukających inspiracji dydaktycznych.

🎯 Cele:
- utrwalenie podstaw: tight vs loose coupling, użycie var, konstrukcja zależności między klasami
- zaproponowanie rozszerzeń tematu (nowe domeny, wyjątki, poziomy trudności, itp.)
-->

---
title: "Zadania praktyczne – Spring Framework: lekcje 11–14"
date: 2025-07-07
lang: pl
slug: master-spring-framework
category: exercises-lesson-11-to-14
---

## ✅ Zadania podstawowe

### 🧩 Zadanie 1: Uruchom pierwszą wersję gry
**Cel:** Zbuduj aplikację z klasami `MarioGame` i `GameRunner` (tight coupling).

**Instrukcje:**
- Utwórz klasę `MarioGame` (pusta lub z metodą `toString()`).
- Utwórz klasę `GameRunner`, która przyjmuje `MarioGame` jako parametr konstruktora.
- W klasie `AppGamingBasic` utwórz obiekty i wywołaj `run()`.

**Rozszerzenie:** Wypisz identyfikator obiektu `MarioGame` w konsoli.

---

### 🧩 Zadanie 2: Dodaj metody sterujące
**Cel:** Rozszerz `MarioGame` o metody `up()`, `down()`, `left()`, `right()`.

**Instrukcje:**
- Dodaj metody, które wypisują różne akcje (np. „Jump”).
- Wywołaj je z klasy `GameRunner`.

**Rozszerzenie:** Zmień kolejność i zachowanie metod (np. dodaj dźwięk, opóźnienie, komunikat debug).

---

### 🧩 Zadanie 3: Użyj `var` w kodzie
**Cel:** Uprość kod, stosując słowo kluczowe `var` (Java 10+).

**Instrukcje:**
- Użyj `var` dla zmiennych lokalnych.
- Wydrukuj typ zmiennej (przez `getClass().getName()` jeśli chcesz sprawdzić).

**Rozszerzenie:** Przetestuj błędne użycie `var` – np. przypisanie `null` lub brak inicjalizacji.

---

### 🧩 Zadanie 4: Dodaj drugą grę – `SuperContraGame`
**Cel:** Stwórz klasę `SuperContraGame` z metodami jak w `MarioGame`.

**Instrukcje:**
- Zaimplementuj analogiczne metody `up()`, `down()`, itd.
- Zmodyfikuj `GameRunner`, aby działał z `SuperContraGame`.

**Rozszerzenie:** Dodaj trzecią grę, np. `PacmanGame`, i przygotuj 3 osobne klasy startowe (`AppGamingBasicX.java`) do uruchamiania każdej.

---

### 🧩 Zadanie 5: Refleksja – tight vs loose coupling
**Cel:** Opisz różnicę między ścisłym a luźnym sprzężeniem klas.

**Instrukcje:**
- Wypisz plusy i minusy obu podejść.
- Posłuż się własnym przykładem z kodu gry.

**Rozszerzenie:** Zaprojektuj nowy scenariusz (np. serwis pogodowy lub kalkulator), w którym tight coupling byłby problemem.

---

## 🔁 Zadania rozszerzające (dla chętnych)

### 🚀 Rozszerzenie A: Zmiana dziedziny – z gier na „Pilot i urządzenia”
**Cel:** Zastąp gry urządzeniami domowymi: `TV`, `Radio`, `Fan`.

**Instrukcje:**
- Każde urządzenie ma metody: `turnOn()`, `turnOff()`, `increaseVolume()`, `decreaseVolume()`.
- Klasa `RemoteControl` działa jak `GameRunner`.

**Efekt:** Lepsze zrozumienie pojęcia zależności i abstrakcji.

---

### 🚀 Rozszerzenie B: Dodaj obsługę błędów
**Cel:** Ulepsz klasy gier, dodając walidację i try catch dla potencjalnych wyjątków.

**Przykład:** Jeśli gra ma `null` jako stan – wyrzuć wyjątek lub wypisz ostrzeżenie.

---

### 🚀 Rozszerzenie C: Dodaj parametr poziomu trudności
**Cel:** Dodaj do każdej gry atrybut `level` (np. EASY, NORMAL, HARD).

**Instrukcje:**
- Użyj `enum` do definiowania poziomów.
- Dodaj logikę zmieniającą zachowanie metod gry w zależności od poziomu.

---

### 🚀 Rozszerzenie D: Użytkownik jako gracz
**Cel:** Dodaj klasę `Player`, która wybiera grę i uruchamia ją.

**Efekt:** Lepsze rozumienie relacji między obiektami (kompozycja i delegacja).

---

📦 Umieść rozwiązania w strukturze folderów np. `02-practical-examples/lesson-11-to-14/`.

🧠 Każde zadanie możesz zapisać również w formie testu jednostkowego lub mini-aplikacji CLI.

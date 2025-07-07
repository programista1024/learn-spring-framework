---
title: "Notatki z lekcji 1–10 kursu Master Spring Framework and Spring Boot"
date: 2025-07-02
lang: pl
slug: master-spring-framework
category: details-lesson-1-to-10
---

## Sekcja 1: Getting Started

### Lekcja 1: Wprowadzenie do kursu

#### Najważniejsze frameworki w świecie Java:
- **Spring Framework**
- **Spring Boot**

#### Problemy początkujących:
- Trudna terminologia (IoC, Dependency Injection, Auto Wiring...)
- Różnorodność zastosowań: Web, REST API, Full Stack, Microservices
- Konieczność poznania dodatkowych narzędzi: Maven, Gradle, Docker, Hibernate, itp.

#### Ścieżka nauki w kursie:
- Podejście praktyczne („hands-on”)
- Ponad 10 projektów na Mavenie i Gradle’u
- Kurs stworzony dla absolutnie początkujących

#### Wskazówki:
- Ucz się aktywnie – rób notatki, przemyślaj zagadnienia
- Powracaj do materiału – przeglądaj prezentacje i przykłady
- Czerp radość z nauki!

### Lekcja 2: Pliki do pobrania

- Flashcards: [in28minutes.com/flashcards](https://www.in28minutes.com/flashcards-list-master-spring-and-spring-boot)
- Repozytorium GitHub: [github.com/in28minutes/master-spring-and-spring-boot](https://github.com/in28minutes/master-spring-and-spring-boot)
- Dodatkowa dokumentacja: [downloads.md](https://github.com/in28minutes/course-material/blob/main/00-master-spring-and-spring-boot/downloads.md)

### Lekcja 3: Instalacja Javy i Eclipse

- Zalecenia:
  - Java 17+ (Spring Boot 3+ nie działa na wcześniejszych wersjach)
  - Eclipse IDE for Enterprise Java Developers
- Instrukcje dla Windows, Linux, Mac

## Sekcja 2: Getting Started with Spring Framework

### Lekcja 7: Po co Spring Framework?
- Redukcja liczby linii kodu
- Pojęcia: *tight coupling*, *loose coupling*, *IoC Container*, *Spring Beans*, *Auto Wiring*

### Lekcja 8: Przegląd zastosowań i plan działania

#### Typy aplikacji:
- Webowe
- REST API
- Full Stack
- Mikroserwisy

#### Cele modułu:
- Zrozumienie kluczowych pojęć Springa
- Zbudowanie prostej aplikacji „gaming app” z różnymi poziomami luźnego powiązania (loose coupling):
  - Iteracja 1: Tightly Coupled Java (GameRunner + konkretna gra)
  - Iteracja 2: Loose Coupling z interfejsem `GamingConsole`
  - Iteracja 3: Spring Beans – kontrola obiektów przez Spring
  - Iteracja 4: Anotacje – pełna automatyzacja (tworzenie, zarządzanie, autowiring)

### Lekcja 9: Tworzenie projektu z użyciem Maven

- Narzędzie: [start.spring.io](https://start.spring.io)
  - Typ: Maven
  - Grupa: `com.in28minutes`
  - Artefakt: `learn-spring-framework`
  - Brak dodatkowych zależności
- Import projektu do Eclipse (może chwilę potrwać)

### Lekcja 10: Spring Initializr i Maven – wprowadzenie

- Spring Initializr: szybkie generowanie szkieletu projektu Spring
- Maven:
  - Narzędzie do zarządzania zależnościami
  - To Maven pobiera dla nas bibliotekę Spring Framework
- Zasada: używaj **stabilnych wersji**, unikaj **snapshotów** (mogą być niestabilne, "under active development")

## 🧠 Quiz – Sprawdź się!
1. Jaki jest cel pola Group ID i Artifact ID w projekcie Spring?
2. Dlaczego nie powinno się używać wersji Snapshot przy nauce?

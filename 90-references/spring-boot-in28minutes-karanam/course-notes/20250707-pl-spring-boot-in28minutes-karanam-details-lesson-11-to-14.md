---
title: "Lekcje 11–14 – Spring Framework: aplikacja Gaming App, var i sprzężenia"
date: 2025-07-07
lang: pl
slug: master-spring-framework
category: details-lesson-11-to-14
---

## Sekcja 3: Spring Framework – część 2

### Lekcja 11 – Krok 04/1: Aplikacja Gaming App – Iteracja 1 (Tight Coupling)

#### Cel:
Stworzenie prostej aplikacji do gry z silnym sprzężeniem między klasami.
Podejście do projektowania Game Runnera do uruchamiania gier takich jak Mario, SuperContra i Pacman obejmuje iteracyjny proces. Pierwsza iteracja wykorzystuje ściśle powiązany kod Java, gdzie klasa GameRunner jest bezpośrednio połączona z konkretnymi klasami gier, takimi jak MarioGame, SuperContraGame czy PacmanGame.

##### Kluczowe pliki:

**`AppGamingBasic.java`**
```java
package com.example.demo;

import com.example.demo.game.GameRunner;
import com.example.demo.game.MarioGame;

public class AppGamingBasic {

	public static void main(String[] args) {
		
		var marioGame = new MarioGame();
		var gameRunner = new GameRunner(marioGame); // GameRunner jest ściśle powiązany z MarioGame
		gameRunner.run();

	}
}
```

**`MarioGame.java`**
```java
package com.example.demo.game;

public class MarioGame {
    // Logika specyficzna dla gry znajdowałaby się tutaj
}
```

**`GameRunner.java`**
```java
package com.example.demo.game;

public class GameRunner {
	MarioGame game; // Bezpośrednio odwołuje się do MarioGame

	public GameRunner(MarioGame game) {
		this.game = game;
	}

	public void run() {
		System.out.println("Running game: " + game); // 
	}
}
```

**Wyjście w konsoli:**
```
Running game: com.example.demo.game.MarioGame@5ca881b5
```

---

### Lekcja 12 – Krok 04/2: Dodanie akcji (przycisków)

Ta lekcja rozszerza klasy MarioGame i GameRunner o podstawowe akcje gry.

**`MarioGame.java`** (rozszerzony o akcje)
```java
public class MarioGame {
    public void up() { System.out.println("Jump"); }
    public void down() { System.out.println("Go into a hole"); }
    public void left() { System.out.println("Go back"); }
    public void right() { System.out.println("Accelerate"); }
}
```

**`GameRunner.java`** (rozszerzony)
```java
public class GameRunner {
    MarioGame game;

    public GameRunner(MarioGame game) {
        this.game = game;
    }

    public void run() {
        System.out.println("Running game: " + game);
        game.up();
        game.down();
        game.left();
        game.right();
    }
}
```

**Wyjście w konsoli:**
```
Running game: com.example.demo.game.MarioGame@5ca881b5
Jump
Go into a hole
Go back
Accelerate
```

---

### Lekcja 13 – Krok 04/3: Wprowadzenie do `var` (Java 10)

#### Najważniejsze informacje:
- Wprowadzone w Javie 10
- Umożliwia **wnioskowanie o typie**
- Upraszcza kod, zmniejsza ilość szablonowego kodu, poprawia czytelność

#### Przykłady:
```java
// Oryginalnie: MarioGame marioGame = new MarioGame();
var marioGame = new MarioGame();

// Oryginalnie: GameRunner gameRunner = new GameRunner(marioGame);
var gameRunner = new GameRunner(marioGame);

// Oryginalnie: List<String> names = List.of("Alice", "Bob", "Charlie");
var names = List.of("Alice", "Bob", "Charlie");

// Inny przykład:
var count = 10; // kompilator wnioskuje 'int'
var message = "Hello, world!"; // kompilator wnioskuje 'String'
```

---

### Lekcja 14 – Krok 05: Luźne vs ścisłe sprzężenie (Loose vs Tight Coupling)

Aby zademonstrować koncepcję powiązania, wprowadzono klasę SuperContraGame.
## SuperContraGame.java
```java
package com.example.demo.game;

public class SuperContraGame {
	public void up() {
		System.out.println("up");
	}
	
	public void down() {
		System.out.println("Sit down");
	}
	
	public void left() {
		System.out.println("Go back");
	}
	
	public void right() {
		System.out.println("Shoot a bullet");
	}
}
```

#### Problem początkowy:
Jeśli spróbujemy użyć `SuperContraGame` z oryginalnym `GameRunner` (który oczekuje `MarioGame`), wystąpi błąd kompilacji.

##### Dlaczego?
`GameRunner` zależy bezpośrednio od klasy `MarioGame`. Aby zadziałało z `SuperContraGame`, trzeba zmodyfikować klasę `GameRunner`.
Błąd kompilacji występuje, ponieważ klasa `GameRunner` w swojej początkowej implementacji jest zaprojektowana do współpracy wyłącznie z obiektami `MarioGame`. Jej konstruktor oczekuje instancji `MarioGame`, a jej wewnętrzna zmienna game jest typu `MarioGame`. Kiedy próbujesz przekazać obiekt `SuperContraGame` do konstruktora `GameRunner`, występuje niezgodność typów, co prowadzi do błędu kompilacji. To demonstruje **ścisłe powiązanie**.

**Zmodyfikowany `GameRunner.java`:**
```java
public class GameRunner {
    private SuperContraGame game;

    public GameRunner(SuperContraGame game) {
        this.game = game;
    }

    public void run() {
        System.out.println("Running game: " + game);
        game.up();
        game.down();
        game.left();
        game.right();
    }
}
```

**`AppGamingBasic.java` (Po modyfikacji GameRunner)**
```java
import com.example.demo.game.GameRunner;
import com.example.demo.game.SuperContraGame;

public class AppGamingBasic {

	public static void main(String[] args) {
		
		// var marioGame = new MarioGame();
		var superContraGame = new SuperContraGame();
		var gameRunner = new GameRunner(superContraGame);
		gameRunner.run();
	}
}
```

**Wyjście w konsoli:**
```
Running game: com.example.demo.game.SuperContraGame@5ca881b5
up
Sit down
Go back
Shoot a bullet
```

---

### Dlaczego powiązanie jest ważne?

- Sprzężenie definiuje, jak bardzo jedna klasa zależy od drugiej.
- Przykłady z życia:
  - Silnik (ściśle sprzężony z samochodem)
  - Koło (luźno sprzężone – można wymieniać)

Powiązanie (coupling) odnosi się do ilości pracy związanej ze zmianą czegoś. Jest to kluczowa koncepcja w tworzeniu oprogramowania:
* **Przykłady ścisłego powiązania z życia wzięte:** Silnik jest ściśle powiązany z samochodem. Komputer stacjonarny jest trudny do przeniesienia.
* **Przykłady luźnego powiązania z życia wzięte:** Koło jest luźno powiązane z samochodem (można je łatwiej wymienić). Laptop jest łatwy do przeniesienia w dowolne miejsce.

#### W oprogramowaniu:
- **Luźne sprzężenie** pozwala na:
  - Łatwiejsze aktualizacje
  - Większą elastyczność
  - Lepsze utrzymanie kodu

W tworzeniu oprogramowania luźne powiązanie jest bardzo pożądane, ponieważ technologia, w tym wymagania biznesowe, frameworki i kod, stale się zmienia. Chcemy wprowadzać zmiany funkcjonalne przy minimalnych modyfikacjach kodu. Interfejsy Java i Spring Framework to narzędzia, które pomagają osiągnąć luźne powiązanie.

#### Wniosek:
GameRunner jest ściśle sprzężony z konkretną grą. Aby użyć innej, trzeba zmodyfikować kod. Następnym krokiem będzie użycie **interfejsów**, aby to uniezależnić.

---

## 🧠 Quiz – Sprawdź się

**P1:** Czym jest ścisłe powiązanie (tight coupling) w kontekście projektowania oprogramowania?
**Odpowiedź:** Ścisłe powiązanie występuje, gdy klasy lub komponenty są od siebie wysoce zależne, co wymaga zmian w jednym elemencie, aby wymusić zmiany w drugim, co czyni system mniej elastycznym.

**P2:** Dlaczego klasa GameRunner jest opisana jako ściśle powiązana w przedstawionym przykładzie?
**Odpowiedź:** Ponieważ jest bezpośrednio zależna od konkretnych implementacji gier, takich jak MarioGame lub SuperContraGame, co wymaga zmian w kodzie w celu przełączania gier.

**P3:** Jaka jest główna wada ścisłego powiązania?
**Odpowiedź:** Sprawia, że kod jest mniej elastyczny i trudniejszy w utrzymaniu, ponieważ zmiany w jednej części kodu często wymagają zmian w innej.

**P4:** Dlaczego luźne powiązanie jest generalnie preferowane w projektowaniu oprogramowania?
**Odpowiedź:** Pozwala na łatwiejsze utrzymanie i elastyczność, umożliwiając zmiany w jednej części systemu z minimalnym wpływem na inne części.

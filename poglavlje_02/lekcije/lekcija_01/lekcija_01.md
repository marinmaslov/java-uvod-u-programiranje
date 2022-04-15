#### Poglavlje 2: Uvod u programiranje 💻

## Lekcija 1
# Pisanje u konzolu 🕹️
---
#### Sadržaj
1.1. [Gdje pisati kod koji želimo izvršiti?](#11-gdje-pisati-kod-koji-želimo-izvršiti)
1.2. [Deklaracija](#22-deklaracija)
1.3. [Inicijalizacija](#23-nicijalizacija)
1.4. [Deklaracija i inicijalizacija](#24-deklaracija-i-inicijalizacija)
1.5. [Primjer deklaracije i inicijalizacije ostalih primitivnih tipova](#25-primjer-deklaracije-i-inicijalizacije-ostalih-primitivnih-tipova)

---

Prije nego što krenemo na konkretne stvari, valja naučiti kako radi ispis u konzolu u Javi.

## 1.1 Gdje pisati kod koji želimo izvršiti?

Već smo rekli da u Javi ništa ne postoji izvan klase. Iako nam nije bitno još što je klasa te što su joj metode, bitno je da je klasa definirana, da se zove isto kao i .java datoteka u kojoj kodiramo te da ona ima `main` metodu.

```Java
public class Klasa {

    public static void main(String[] args) {
		// ovdje ide naš kod kojeg želimo izvršiti
    }
}
```

## 1.2 Naredba za ispis
Svaki Java program sadrži naredbe (eng. statements), a svaka naredba opisuje neku operaciju koju računalo treba izvršiti (ispis na zaslon, računaska operacija, provjera položaja miša na zaslonu itd.).

Naredba kojom ispisujemo stvari u konzolu tj. na zaslon je:

```Java
System.out.println("Hello, World.");
```

Primijetimo kako sve riječi koje ispisujemo pomoću ove naredbe unutar dvostrukih navodnika ("..."). **Riječi se uvijek u Javi moraju nalaziti unutar navodnika!**

Nju, kao i bilo što što definiramo, moramo pozvati u `main` metodi klase, u suprotnom se neće izvršiti. Stoga naredbu za ispis ubacujemo u `main` metodu:

```Java
public class Klasa {

    public static void main(String[] args) {
		System.out.println("Hello, World.");
    }
}
```

Ako sad pokrenemo kod, u konzoli će nam se ispisati:

```
Hello, World.
```

## 1.3 Više naredbi za ispis
Pomno promotrimo još jednom naredbu za ispit te se usredotočimo na `.println()` dio. Taj dio govori da će se ono što smo stavili unutar zagrada ispisati u jednoj liniji nakon čega će mo se prebaciti odmah u sljedeću liniju ("print line").

Da smo tu istu naredbu pozvali dva puta, jednu za drugom:

```Java
public class Klasa {

    public static void main(String[] args) {
		System.out.println("Hello, World.");
		System.out.println("Hello, Java.");
    }
}
```

Ispis bi nam bio:

```
Hello, World.
Hello, Java.
```

Osim `.println()`, imate još i `.print()`, koji za razliku od `.println()` nakon izvršavanja ne prelazi u novi red, pa da smo pozvali `.print()` naredbu prije `.println()`:

```Java
public class Klasa {

    public static void main(String[] args) {
		System.out.print("Hello, World.");
		System.out.println("Hello, Java.");
    }
}
```

Ispis bi nam bio:

```
Hello, World.Hello, Java.
```

## 1.4 Formatiranje ispisa
Gore smo u primjerima ispisivali riječi i rečenike i one su uvijek bile unutar navodnika. Jedna zanimljivost koju u Javi možete je zbrajati riječi, tj. nadovezivati rečenice i riječi jedne na druge.

Recimo da želimo imamo sljedeće dvije rečenice:
`Danas je suncan dan!` i `No sutra najavljuju kisu.`

Ako ih želimo obje ispisati u istoj naredbi, možemo ih, doslovno zbrojiti:

```Java
public class Klasa {

    public static void main(String[] args) {
		System.out.print("Danas je suncan dan!" + "No sutra najavljuju kisu.");
    }
}
```

Ispis će bit sljedeći:

```
Danas je suncan dan!No sutra najavljuju kisu.
```

Zašto ne postoji razmak između rečenica? Jednostavno. Pogledajmo prvu rečenicu koju smo dali naredbi: "Danas je suncan dan!" i pogledajmo drugu: "No sutra najavljuju kisu.". 

Rečenice su omeđene navodnicima. Ono što kompajler radi je da na kraj prve zalijepi početak druge rečenice, a postoji li na kraju prve ili na početku druge rečenice razmak (a da je on unutar navodnika)? 

Ne postoji, ako želimo da postoji razmak, dodajmo ga. Razmaci su isto znakovi, te su dio rečenice. Sasvim je svejedno hoćemo li razmak dodat na početak druge rečenice

```Java
System.out.print("Danas je suncan dan!" + " No sutra najavljuju kisu.");
```

Ili na kraj prve:

```Java
System.out.print("Danas je suncan dan! " + "No sutra najavljuju kisu.");
```

Ispis će nam sada biti:

```
Danas je suncan dan! No sutra najavljuju kisu.
```

Postoji još nešto što smo mogli napraiviti. Razmak je znak. Tko mu brani da i sam bude rečenica. Nama nitko ne brani dati ovo naredbi za ispis:

```Java
System.out.print(" ");
```

Ovo će se uredno ispisati kao:

```
 
```

Na prvu vam se čini kao da se nije ništa ispisalo, al označite taj prazni pravokutnik mišom. Vidjet ćete da tu postoji znak - razmak (whitespace)!

Zato možemo napraviti i ovo:

```Java
public class Klasa {

    public static void main(String[] args) {
		System.out.print("Danas je suncan dan!" + " " + "No sutra najavljuju kisu.");
    }
}
```

I s time ćemo dobiti isto što i kad smo razmak dodali na kraj prve ili na početak druge rečenice:

```
Danas je suncan dan! No sutra najavljuju kisu.
```

## 1.5 Posebni znakovi
Osim rečenica koje ispisujete na zaslonu, te "praznih" rečenica koje ste vidjeli poviše, postoji još nešto, a to su posebni znakovi.

Dva su. Znak za novu liniju i znak za tabularni razmak.

Recimo da smo prisiljeni koristit naredbu `System.out.print()` za ispis dviju rečenica, al baš želimo da se druga rečenica prebaci u novi red.

Tu nam u igru ulazi znak `\n` koji označava novi red.

Ako sada pokrenemo kod gdje smo na kraj prve rečenice stavili taj znak:

```Java
public class Klasa {

    public static void main(String[] args) {
		System.out.print("Danas je suncan dan!\n");
		System.out.print("No sutra najavljuju kisu.");
    }
}
```

Ispis će nam biti:

```
Danas je suncan dan!
No sutra najavljuju kisu.
```

Recimo sad da želimo ispisati te dvije rečenice u istoj liniji, ali ne s jednim razmakom između njih već s 8 razmaka, tada možemo koristiti posebni znak `\t`:

```Java
public class Klasa {

    public static void main(String[] args) {
		System.out.print("Danas je suncan dan!\t");
		System.out.print("No sutra najavljuju kisu.");
    }
}
```

Ispis je sada:

```
Danas je suncan dan!	No sutra najavljuju kisu.
```

Ako se sad pitate: "Zašto nije druga rečenica u drugom redu? Pa korištene su dvije naredbe za ispis.". Pogledajte koja naredba za ispis je korištena. Da, `print()` koji ne prebacuje u novi red.

Također, znak `\` koji vidite i u znaku `\n` i u znaku `\t` ima svoje značenje.

Zamislite da želimo ispisati rečenicu: Marko "dobro" pleše. Baš to s navodnicima. Kako bismo to napravili? Ovako možda:

```Java
public class Klasa {

    public static void main(String[] args) {
		System.out.println("Marko "dobro" pleše");
    }
}
```

Ovo će izbaciti grešku. Zašto? Sjetimo se što smo rekli: rečenice uvijek moraju biti u navodnicima. Što se gore dogodilo? izbacili smo jedan dio rečenice, tj. riječ `dobro` izvan rečenice, pa sada imamo rečenice: `"Marko "`, riječ dobro (koja visi u zraku) i ˙`" pleše"`.

**Kako ovo popraviti? Tu u igru dolazi znak** `\`**.** On nam služi da bismo kompajleru rekli: "Ej, znak koji ti slijedi iza `\` nije onaj znak kojeg misliš da je."

Što to znači?

Zamislite da smo gore u primjerima `\n` i `\t` napisali bez toga `\` onda bi to bila obična slova `n` i `t` dok su s tim znakom ispred (`\`) predstavljali novi red i tabularni razmak.

Isto tako možemo popraviti naš problem. Koristeći `\` ćemo kompajleru reći: "Ej, nije ti taj navodnik tu zato što prekidam rečenicu već zato što želim ispisat navodnike na tom mjestu."

Ako sada dodamo taj znak ispred ta dva navodnika:

```Java
public class Klasa {

    public static void main(String[] args) {
		System.out.println("Marko \"dobro\" pleše");
    }
}
```

Ispis će nam biti:

```
Marko "dobro" pleše
```


## 1.6 Zadaci za vježbu ✏️
### Zadatak 1:
Napišite program koji na zaslon ispisuje: "Pozdrav, ja sam `vaše ime i prezime`" i "dolazim iz `mjesto odakle ste`". Ali tako da prvu rečenicu ispišete pomoću naredbe `System.out.print()`, a drugu pomoću `System.out.println()` pri čemu pripazite da rečenice ne budu slijepjene već da budu razmaknute!

Rješenje možete provjeriti ovdje.

### Zadatak 2:
Napišite program koji će na zaslonu dati sljedeći ispis:

```
+-------------+
+ vaše ime    +
+ "datum"     +
	+-------------+
```

Datum treba biti u navodnicima.

Također, koristite samo `System.out.print()` naredbu, te naglasak: taj razmak u zadnjoj liniji nije greška!

Rješenje možete provjeriti ovdje.

## 1.7 Sažetak 🎯
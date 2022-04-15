#### Poglavlje 2: Uvod u programiranje 💻

## Lekcija 4
# Čitanje s konzole 🕹️
---
#### Sadržaj
1.1. [Gdje pisati kod koji želimo izvršiti?](#11-gdje-pisati-kod-koji-želimo-izvršiti)
1.2. [Deklaracija](#22-deklaracija)
1.3. [Inicijalizacija](#23-nicijalizacija)
1.4. [Deklaracija i inicijalizacija](#24-deklaracija-i-inicijalizacija)
1.5. [Primjer deklaracije i inicijalizacije ostalih primitivnih tipova](#25-primjer-deklaracije-i-inicijalizacije-ostalih-primitivnih-tipova)

---

Sada kad smo naučili kako pisati u konzolu te što su varijable i kako ih mijenjati, možemo krenuti na čitanje korisnikovog unosa s konzole.

U nastavku ćemo proći par osnova o klasama i objektima, no nećemo previše duboko ulaziti u njih jer ćemo za nekoliko poglavlja tek objašnjavati koncepte objekto orijentiranih jezika.

## 4.1 Uvoz klase Scanner
Čitanje s konzole se u Javi odvija preko klase Scanner. Kako bimo koristili Scanner moramo ga uvesti u naš projekt, a to radimo izvan klase tako da navedemo ključnu riječ `ìmport` i navedemo putanju kroz pakete do same klase, pri čemu paket, podpakete i samu klasu odvajamo s točkom, i to na sljedeći način:

```Java
import paket1.podpaket2.(...).podpaketN.ImeKlase;
```

Uvoz klase Scanner izgleda ovako:

```Java
import java.util.Scanner;

public class Klasa
{
	public static void main(String[] args) {
		// ovdje ide kod kojeg izvršavamo
	}
}
```

## 4.2 Stvaranje Scanner objekta
Kako bismo stvorili naš objekt za čitanje unosa s konzole, potrebno je **deklarirati** varijablu tipa Scanner (uočite da radimo s ne-primitivnim tipom podatka):

```Java
import java.util.Scanner;

public class Klasa
{
	public static void main(String[] args) {
		Scanner citac;
	}
}
```

Iako **deklaracija** jako podsjeća na deklaraciju primitivnih tipova podataka, inicijalizacija se značajno razlikuje.

Kako bismo inicijalizirali naš `citac` potrebno je napisati sljedeće:

```Java
import java.util.Scanner;

public class Klasa
{
	public static void main(String[] args) {
		Scanner citac;
		citac = new Scanner(System.in);
	}
}
```

Da pojasnimo malo što se ovdje događa. 

Kada inicijaliziramo varijablu primitivnog tipa npr. `int` to izgledao ovako:

```Java
int cijeliBroj = 10;
```

Kompajleru govorimo da je tipa `ìnt`, dajemo joj ime i pridodjeljujemo joj vrijednost 10 (zbog toga se i zovu primitivni tipovi jer barataju s primitivnim podacima).

Kod deklaracije objekata kompajleru govorimo od koje klase instanciramo objekt. Dakle stvaramo varijablu tj. objekt tipa `Scanner` (uočite i tu ono što smo rekli u lekciji prije da se ne-primitivni tipovi podataka pišu velikim početnim slovom).

```Java
Scanner citac;
```

E sada... Za razliku od inicijalizacije primitivnih tipova, kod ne-primitivnih stvaramo instancu klase čijeg su tipa.

Insancu stvaramo pomoću ključne riječi `new` zatim navodimo klasu od koje instanciramo objekt i to sa zagradama u kojem možemo proslijediti neke parametra, ako su potrebni, a kod Scanner klase jesu. Ono što joj prosljeđujemo kao parametar je predefinirani objekt `System.in` koji predstavlja standardni ulazni tok u program.

```Java
citac = new Scanner(System.in);
```

## 4.3 Čitanje linije s konzole
Sada kada smo stvorili naš Scanner objekt možemo nešto i pročitati.

Čitanje se odvija pozivanjem metode `.nextLine()` na sljedeći način:

```Java
String userName = citac.nextLine();
```







#### Poglavlje 2: Uvod u programiranje 💻

## Lekcija 2


# Tipovi podataka 🗄️
#### Sadržaj
1. [Varijable](#21-varijable)
2. [Deklaracija](#22-deklaracija)
3. [Inicijalizacija](#23-nicijalizacija)
4. [Deklaracija i inicijalizacija](#24-deklaracija-i-inicijalizacija)
5. [Primjer deklaracije i inicijalizacije ostalih primitivnih tipova](#25-primjer-deklaracije-i-inicijalizacije-ostalih-primitivnih-tipova)
	1. [Byte, short i long](#251-byte-short-i-long)
	2. [Float i double](#252-float-i-double)
	3. [Char](#253-char)
	4. [Boolean](#254-boolean)
6. [Promjena vrijednosti varijable](#26-promjena-vrijednosti-varijable)
7. [Konstante](#27-konstante)
8. [Zadaci za vježbu](#28-zadaci-za-vježbu)
9. [Sažetak](#29-sažetak)


Postoje dvije vrste podataka (ne samo u Javi već većini programskih jezika), a to su: `primitivni tipovi` i `ne-primitivni tipovi`.

Primitivni tip podatka definira veličinu i tip vrijednosti koja se pohranjuje u varijabli, te nema nikakve dodatne metode koje su mu pridružene.

U Javi imamo 8 primitivnih tipova podataka, a oni su:

| Tip podatka | Veličina | Opis |
| ----------- | ----------- | ----------- |
| byte | 1 bajt | Pohranjuje cijele brojeve od -128 do 127 |
| short | 2 bajta | Pohranjuje cijele brojeve od -32768 do 32767 |
| int | 4 bajta | Pohranjuje cijele brojeve od -2147483648 do 2147483647 |
| long | 8 bajtova | Pohranjuje cijele brojeve od  -9223372036854775808 do 9223372036854775807 |
| float | 4 bajta |  Pohranjuje decimalne brojeve, te ide do 6-7 decimalnih mjesta |
| double | 6 bajtova | Pohranjuje decimalne brojeve, te ide do 15 decimalnih mjesta |
| boolean | 1 bit | Pohranjuje vrijednost: true (istina) ili false (laž) |
| char | 2 bajta | Pohranjuje jedan znak |

Ne-primitivni tipovi podataka se odnose na objekte (koje ćemo obraditi malo kasnije). Oni ne pohranjuju vrijednost varijable izravno u memoriji, već pohranjuju adresu varijable u memoriji (ono zapravo pokazuju na lokaciju u memoriji na kojoj se neki podatak nalazi). Za razliku od primitivnih tipova, kojih je u Javi fiksno 8 - ne može ih se stvoriti više, ne-primitivini tipovi su definirani od strane programera, pa im se zbog toga može pridodijeliti i `null` što govori da oni ni na što ne pokazuju.

Ključna razlika među `primitivnim` i `ne-primitivnim` tipovima podataka u Javi je ta što se primitivni pišu malim slovom (`int`, `float`, `boolean`...), dok se ne-primitivni pišu velikim početnim slovom (npr. `String`, `Array`, `Class`, `Interface`).

![Tipovi podataka](img_001_data_types.png)


### 2.1 Varijable
Varijable su spremnici koje koristimo za čuvanje podataka. Zašto bismo to htjeli raditi? Tijekom programiranja ćemo stalno baratati s podacima pa ih želimo imati stalno dostupne. Zato ih pohranjujemo u varijable.

Kako bi nam ti pohranjeni podaci bili razumljivi varijablama (spremnicima) pridodajemo imena. Ta imena se u Javi pišu na specifičan način koji se zove `CamelCase` i on govori da se imena varijabli pišu tako da se prva riječ napiše malim početnim slovom, a sve ostale riječi velikim početnim slovom, a među riječima ne postoji razmak. Također, koriste se samo slova engleske abecede, pa zaboravite na postojanje `ć`, `č`, `đ`, `š`, i `ž`.

Prema tome, ako želimo definirati varijablu imena `godina rođenja`, pišemo:

```Java
	godinaRodenja
```

### 2.2 Deklaracija
Deklaracija varijabli zahtjeva i definiciju tipa. Kao što je rečeno, varijable su spremnici u kojima čuvamo podatke, no Java ne zna koji podatak mi želimo čuvati u našoj varijabli, tj. Java ne zna koliko mjesta u memoriji će zauzeti za taj naš podataka, pa joj mi to ekspilicitno govorimo tako da ispred imena varijable dopišemo i `osnovni tip`. Drugi tip varijabli su Java klase (ne-primitivni tipovi), ali o tome ćemo nešto kasnije pričati.

Kako smo našu varijablu nazvali `godinaRodenja`, jasno je da je riječ o cijelom broju, pa ćemo to Javi naglasiti tako što ćemo joj reći: "Hej. Stvori mi spremnik imena `godinaRodenja` u kojem planiram čuvati cijeli broj tj. `int`", i to na sljedeći način:

```Java
	int godinaRodenja;
```

### 2.3 Inicijalizacija
Sada smo uspješno `deklarirali` našu varijabu imena `godinaRodenja`. No, nismo još gotovi. Osim `deklaracije`, u kojoj Javi govorimo "Stvori mi to spremink tog imena i u njemu drži taj tip podatka", valja tu varijablu i `inicijalizirati` - pridodijeliti vrijednost toj varijabli, tj. pohraniti nešto u taj spremnik.

To radimo na sljedeći način. Započinjemo novu liniju koda u kojoj pozivamo našu varijablu  `godinaRodenja` te pomoću znaka jednakosti u nju spremamo cijeli broj `1997`. 

```Java
	godinaRodenja = 1997;
```

**Pripazite!** Kako smo varijablu  `godinaRodenja` definirali da je tipa `int`, njoj možemo pridodijeliti isključivo cijele brojeve. Decimalni brojevi, znakovi ili boolean vrijednost se u nju ne mogu spremiti. Da to pokušate dobili biste grešku `incompatible types`.

### 2.4 Deklaracija i inicijalizacija
Sada kad smo uspješno deklarirali i inicijalizirali našu varijablu možemo vam otkritit jednu tajnu: deklaracija i inicijalizacija se nisu morale raditi u dvije odvojene linije, mogli ste oboje odraditi u jednoj na sljedeći način:

```Java
	int godinaRodenja = 1997;
```

### 2.5 Primjer deklaracije i inicijalizacije ostalih primitivnih tipova
Gore smo u primjeru pokazali kako se deklarira i inicijalizira varijabla tipa int. Što je s drugim tipovima?

Pa... Vrijedi sve što vrijedi i za int - deklariraju se i inicijaliziraju na isti način, uz neka manje dodatna pravila.

#### 2.5.1 Byte, short i long
Poput `int`-a, varijable tipa `byte` i `short` se deklariraju i inicijaliziraju na isti način:

```Java
	byte manjiBroj = 3;
	short nestoVeciBroj = 500;
```

Iznimka je kad inicijaliziramo varijablu tipa `long`. Java nije glupa, neće tek tako bezveze zauzeti 8 bajtova memroije (danas se to čini kao malo, al 90-ih je to bilo iznimno puno memorije). Po osnovi su svi cijeli brojevi u Javi int, osim ako se ekspilicno ne navede drugačije

Zato će vam kad pokušate napraviti sljedeće:

```Java
	long ogromanBroj = 78461874534534534;
```

Javiti grešku:

```
	error: integer number too large
```

Kako biste uspješno deklalirali i inicijalizirali varijablu tipa `long` potrebno je na kraju tog cijelog broja navesti znak `L`.

```Java
	long ogromanBroj = 78461874534534534L;
```

Međutim, u Javi se svi cijeli brojevi u osnovi tretiraju kao `int`, pa ćemo kasnije kad budemo pokazivali **matematičke operacije** nad varijablama pokazati što ovdje sve može poći po zlu kad korstimo nešto drugo osim `int`-a za pohranu cijelog broja.

#### 2.5.2 Float i double
Kako se u osnovi svi cijeli brojevi u Javi tretiraju kao `int`, ako se i razlomljeni brojevi tretiraju kao `dobule`, pa ćemo ako želimo inicijalizirati varijablu tipa `float` morat to i eksplicitno navesti tako da na kraju broja dodamo slobo `F`.

Primjer deklaracije i inicijalizacije razlomljenih brojeva:

```Java
	float manjiRazlomljeniBroj = 4324.4234F;
	double veciRazlomljeniBroj = 432.3534562653456;
```

#### 2.5.3 Char
Kao što smo već rekli char može držati samo jedan znak, pa se prema tome deklarira i inicijalizira na sljedeći način:

```Java
	char znak = 'z';
```

Uočite da se taj znak mora nalaziti, pri inicijalizaciji, unutar jednkratih navodnika.

Također, znakovi nisu samo slova. Namjerno smo napisalo znak, jer možete i ovo napraviti:

```Java
	char znakBroj = '5';
	char znakPosebni = '*';
	char znakRazmak = ' ';
```

Da. Razmak je isto znak! 😃

#### 2.5.4 Boolean
Primitivni tip boolean može biti samo jedna od dvije stvari: istina ili laž.

Prema tome, neka imamo varijable tipa boolean: `istina` i `laz`. Deklariramo i inicijaliziramo ih ovako:

```Java
	boolean istina = true;
	boolean laz = false;
```

### 2.6 Promjena vrijednosti varijable
Kao što samo ime sugerira, varijable nisu upisan u kamen nakon što ih inicijaliziramo. Što to znači? To znači da ih možemo mijenjati do mile volje.

Uzmimo za primjer našu varijablu `godinaRodenja` tipa `int`. Ako je ispišemo u konzolu:

```Java
	int godinaRodenja = 1997;
	System.out.println("Godina rodenja je: " + godinaRodenja);
```

Dobit ćemo:

```
	Godina rodenja je: 1997
```

Promijenimo sada vrijednost toj našoj varijabli u `1998`, ispišimo je, te joj još jednom prmijenimo vrijednost u `1999` i ponovo je ispišimo.

```Java
	godinaRodenja = 1998;
	System.out.println("Godina rodenja je: " + godinaRodenja);
	godinaRodenja = 1999;
	System.out.println("Godina rodenja je: " + godinaRodenja);
```

Ispis je:

```
	Godina rodenja je: 1998
	Godina rodenja je: 1999
```

Primijetite kako pri promjeni vrijednosti varijabli ne trebamo definirati (pisati) tip ispred imena varijable. To je zato što je ona već deklarirana u bloku koda prije. Jednom deklarirana varijabla se ne može ponovo deklarirati, ali joj se vrijednost može mijenjati. Ako ne vjerujete probajte dva puta deklarirati varijablu istog imena i vidite koja se greška javlja!

Naglasak: U primjeru smo koristili varijablu tipa `int`, ali se mogao koristit bilo koji tip. Nemojte misliti da je samo `int` promjenjiv, svaka varijabla je promjenjiva. Ono što nije promjenjivo slijedi u nastavku.

### 2.7 Konstante
Osim varijabli, koje su promjenjive, imamo i konstante, kojima se, nakon što ih se deklarira i inicijalizira, više ne može promijeniti vrijednost.


### 2.8 Zadaci za vježbu
### 2.9 Sažetak
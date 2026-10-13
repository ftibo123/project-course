# Project outline: "[[00-project/01-project-outline]]"

## Specification – Kamerás kirakósegéd hiányzó puzzle-darabok kereséséhez

## 1. Szereplők és jogosultságok

A rendszer elsődleges szereplője a felhasználó, aki fényképek segítségével szeretné megtalálni egy kirakó hiányzó darabját.

A felhasználó projekteket hozhat létre és menthet el, képeket készíthet vagy tölthet fel, ellenőrizheti és javíthatja a felismert darabokat, megtekintheti a lehetséges találatokat, valamint jóváhagyhatja vagy visszavonhatja a kiválasztott darab elhelyezését.

A fejlesztő feladata az alkalmazás megvalósítása, tesztelése és dokumentálása.

## 2. Use case-ek és user storyk

### UC1 – Projekt létrehozása és folytatása

A felhasználó létrehoz egy projektet, majd képeket készít vagy tölt fel a rendelkezésre álló puzzle-darabokról. A rendszer elmenti a projekt adatait és a hozzá tartozó képeket, így a munka később folytatható.

**User story:** Felhasználóként szeretném elmenteni a kirakóval kapcsolatos munkámat, hogy később onnan folytathassam, ahol abbahagytam.

### UC2 – A darabok és a hiányzó hely felismerése

A rendszer megpróbálja elkülöníteni a különálló darabokat a háttértől, és felismerni a kirakóban található hiányzó hely körvonalát. A felhasználó szükség esetén javíthatja a felismert kontúrokat és a kijelölést.

**User story:** Felhasználóként szeretném ellenőrizni és javítani a felismert alakzatokat, hogy a keresés megfelelő bemeneti adatok alapján történjen.

### UC3 – A megfelelő darab megkeresése

A rendszer összehasonlítja a rendelkezésre álló darabokat a hiányzó hellyel. Figyelembe veszi a geometriai illeszkedést, a lehetséges elforgatásokat, valamint a szomszédos darabok határainak szín- és képi jellemzőit. A legjobb jelölteket rangsorolva jeleníti meg.

**User story:** Felhasználóként szeretném látni a legígéretesebb darabokat és az illeszkedésük vizuális összehasonlítását, hogy könnyebben kiválaszthassam a megfelelő elemet.

## 3. Funkcionális követelmények

| Azonosító | Követelmény |
|---|---|
| FR-01 | A rendszer lehetővé teszi projektek létrehozását, mentését és folytatását. |
| FR-02 | A felhasználó mobiltelefonról képet készíthet, illetve meglévő képet tölthet fel. |
| FR-03 | A rendszer megőrzi az eredeti képeket, a felismert darabokat és azok azonosítóit. |
| FR-04 | A rendszer automatikusan megpróbálja elkülöníteni a darabokat, és megjeleníti azok kontúrját. |
| FR-05 | A felhasználó kézzel javíthatja a felismert darabok körvonalát és a hiányzó hely kijelölését. |
| FR-06 | A rendszer támogatja a perspektíva és a méretarány korrekcióját referencia alapján vagy megadott kalibrációs pontokkal. |
| FR-07 | A rendszer geometriai és képi jellemzők alapján rangsorolja a lehetséges darabokat és elforgatásaikat. |
| FR-08 | A találatoknál külön megjeleníti a geometriai és a képi egyezés pontszámát, valamint a vizuális illeszkedést. |
| FR-09 | A rendszer figyelmeztet, ha a képek minősége nem megfelelő, vagy a találatok bizonytalanok. |
| FR-10 | A felhasználó jóváhagyhatja a kiválasztott darabot, és vissza is vonhatja az elhelyezést. |
| FR-11 | Ugyanaz a darab nem rendelhető egyszerre több aktív elhelyezéshez. |
| FR-12 | A kontúr vagy a hiányzó hely módosítása esetén a rendszer érvényteleníti az elavult keresési eredményeket. |
| FR-13 | A rendszer lehetővé teszi az illesztési algoritmus eredményességének tesztelését ellenőrzött adatokon. |

## 4. Üzleti szabályok és korlátok

- A rendszer első változata hagyományos, sík, körülbelül 24–100 darabos kirakók támogatására készül.
- A keresés egyetlen, teljesen körülhatárolt belső hiányzó helyre koncentrál, amelyet minden oldalról szomszédos darabok vesznek körül.
- A bemeneti képen a különálló darabok nem fedhetik egymást, és lehetőleg egyszínű, jól elkülönülő háttérre kell helyezni őket.
- A fényképezés körülményeit dokumentálni kell, a geometriai összehasonlításhoz pedig szükség esetén korrigálni kell a perspektívát és a méretarányt.
- Az illesztés során a hiányzó hely minden rendelkezésre álló szomszédját és a darabok lehetséges elforgatásait figyelembe kell venni.
- A pontszámok az egyezés mértékét jelzik, nem a helyesség valószínűségét.
- A rendszernek kezelnie kell azt az esetet is, amikor a megfelelő darab nem található meg a rendelkezésre álló elemek között.
- A darabokhoz és a találatokhoz tartozó adatoknak visszakövethetőnek kell maradniuk az eredeti fényképig.

## 5. Felhasználói felület és munkafolyamat

Az alkalmazás reszponzív webes felületen működik, és mobiltelefonon is használható.

A fő munkafolyamat:

1. A felhasználó létrehoz vagy megnyit egy projektet.
2. Fényképet készít vagy feltölti a rendelkezésre álló darabokat.
3. Ellenőrzi és szükség esetén javítja a felismert kontúrokat.
4. Képet készít a részben összeállított kirakóról, majd kijelöli vagy javítja a hiányzó helyet.
5. Elvégzi a szükséges geometriai kalibrációt.
6. Elindítja a keresést, majd megtekinti a rangsorolt találatokat és az illeszkedés vizuális összehasonlítását.
7. Jóváhagyja vagy visszavonja a kiválasztott darabot, illetve szükség esetén új képpel megismétli a keresést.

A felületnek egyértelműen jeleznie kell a hibás képeket, a bizonytalan találatokat és a jóváhagyott elhelyezéseket.

## 6. Nem funkcionális követelmények

- **Használhatóság:** A felület legyen áttekinthető, reszponzív és mobiltelefonon is kezelhető.
- **Megbízhatóság:** A projektadatok és az eredeti képek maradjanak meg sikertelen feldolgozás esetén is.
- **Teljesítmény:** A keresés működjön megfelelő sebességgel a támogatott, legfeljebb 100 darabos feladatoknál.
- **Karbantarthatóság:** A képfeldolgozás, a geometriai illesztés és a rangsorolás különálló, tesztelhető modulokban valósuljon meg.
- **Tesztelhetőség:** Az algoritmusok eredményei ellenőrizhetőek és összehasonlíthatóak legyenek.
- **Adatkezelés:** A képek és a felhasználói módosítások tárolása legyen biztonságos és visszaállítható.

## 7. Nyitott kérdések és kockázatok

A fejlesztés során meg kell vizsgálni, hogy mely képszegmentálási módszerek működnek megbízhatóan különböző fényviszonyok és háttérszínek mellett. További kérdés a geometriai és képi pontszámok megfelelő kombinálása, valamint az ismétlődő mintázatok, a közel szimmetrikus darabok és a bizonytalan találatok kezelése.

A rendszer értékeléséhez több különböző kirakóból származó, kézzel ellenőrzött tesztadatokat kell készíteni. Össze kell hasonlítani a kizárólag geometriai illesztésre épülő alapmegoldást a geometriai és képi jellemzőket kombináló módszerrel. A vizsgálat fő szempontjai a helyes első találat aránya, a helyes darab első öt találat közötti megjelenése, a nem létező megoldások felismerése és a keresési idő.

A teljes kirakó automatikus összeállítása, a dobozkép felhasználása és több hiányzó hely egyidejű keresése nem része a kötelező első változatnak.

## 8. Kezdeti technikai javaslat

A rendszer egy webes felületből és egy Rust-alapú backendből áll.

- **Frontend:** React és TypeScript a reszponzív felülethez, a képek megjelenítéséhez és a kontúrok szerkesztéséhez.
- **Backend:** Rust és Axum a HTTP API, a projektek kezelése és a keresési folyamat megvalósításához.
- **Képfeldolgozás:** OpenCV Rust-kötéseken keresztül a képek előfeldolgozásához, a szegmentáláshoz és a geometriai műveletekhez.
- **Illesztési algoritmus:** Saját fejlesztésű Rust-modul a darabok kontúrjainak, elforgatásainak és képi jellemzőinek összehasonlítására, valamint a jelöltek rangsorolására.
- **Adattárolás:** SQLite a projektadatokhoz és fájlrendszer az eredeti, illetve feldolgozott képek tárolására.
- **Tesztelés és verziókezelés:** Automatizált tesztek, Git és GitHub.

A megvalósítás során elsőként a képfeldolgozási és geometriai illesztési folyamatot érdemes prototípusként elkészíteni. Ezt követően integrálható a webes felülettel és a projektadatok tárolásával.

A projekt fő célja egy olyan működő, tesztelhető alkalmazás elkészítése, amely képek alapján megkeresi és rangsorolja a hiányzó helyhez leginkább illeszkedő puzzle-darabokat, miközben a végső döntést a felhasználóra bízza.
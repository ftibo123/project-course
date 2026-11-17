# Kamerás kirakósegéd hiányzó puzzle-darabok kereséséhez

Szerző: Farkas Tibor 
Neptun: DOHOLH
Témavezető: Sári Dávid
Projektazonosító: 2026-SD-04

---

## A specifikáció összefoglalása

A projekt célja egy reszponzív webalkalmazás fejlesztése, amely fényképek alapján segít megtalálni egy részben összeállított kirakó egyetlen hiányzó belső darabját.

A rendszer lehetővé teszi projektek létrehozását és mentését, képek feltöltését, a puzzle-darabok felismerését, valamint a hiányzó hely kijelölését. A keresés során geometriai és képi jellemzők alapján rangsorolja a lehetséges darabokat és azok elforgatásait.

Az első változat 24–100 darabos, síkbeli kirakókra összpontosít. A végső darab kiválasztása és behelyezésének jóváhagyása minden esetben a felhasználó feladata.

## Fő felhasználói utak és követelmények

A rendszer három fő felhasználói folyamatra épül:

1. **Projekt létrehozása:** A felhasználó létrehoz vagy megnyit egy projektet, majd képeket készít vagy tölt fel a puzzle-darabokról. A rendszer elmenti a képeket és a projekt adatait.
2. **Darabok és hiányzó hely felismerése:** A rendszer megpróbálja elkülöníteni a darabokat a háttértől, meghatározza a kontúrjaikat, és lehetőséget biztosít azok kézi javítására.
3. **Megfelelő darab keresése:** A rendszer geometriai és képi illeszkedés alapján rangsorolja a jelölteket, megjeleníti a pontszámokat és a vizuális összehasonlítást. A felhasználó jóváhagyhatja vagy visszavonhatja a behelyezést.

A legfontosabb funkcionális követelmények a képfeltöltés, a szegmentálás, a kontúrszerkesztés, a geometriai kalibráció, a találatok rangsorolása és a projektállapot mentése.

## Kezdeti technikai javaslat

A rendszer egy frontendből, egy backendből és egy képfeldolgozó, illetve illesztési komponensből áll.

- **Frontend:** React és TypeScript a reszponzív felülethez, a képek megjelenítéséhez és a kontúrok szerkesztéséhez.
- **Backend:** Rust és Axum a HTTP API, a projektkezelés és a keresési folyamat megvalósításához.
- **Képfeldolgozás:** OpenCV a képek előfeldolgozásához, a darabok szegmentálásához és a kontúrok felismeréséhez.
- **Illesztési algoritmus:** Saját fejlesztésű Rust-modul a darabok alakjának, elforgatásának és képi jellemzőinek összehasonlítására.
- **Adattárolás:** SQLite a projektadatokhoz, fájlrendszer az eredeti és feldolgozott képekhez.
- **Verziókezelés és tesztelés:** Git, GitHub és automatizált tesztek.

A képfeldolgozás, az illesztési algoritmus és a projektállapot kezelése különálló, tesztelhető komponensként valósulna meg.

## A 2. félév megvalósítási terve

1. **Képfeldolgozási prototípus:** A puzzle-darabok szegmentálása, maszkok és kontúrok előállítása.
2. **Geometriai illesztés:** A darabok alakjának összehasonlítása, elforgatások vizsgálata és az első rangsorolási algoritmus elkészítése.
3. **Képi illesztés:** A szomszédos darabok színeinek és képi jellemzőinek figyelembevétele a rangsorolásban.
4. **Kalibráció és felhasználói felület:** Perspektívakorrekció, kontúrok kézi javítása és a reszponzív frontend elkészítése.
5. **Projektkezelés és integráció:** Mentés, visszaállítás, keresési eredmények kezelése és a komponensek összekapcsolása.
6. **Tesztelés és kiértékelés:** Az algoritmus vizsgálata több különböző kirakón, ellenőrzött adatok alapján.

## Nyitott kockázatok és következő lépések

A legfontosabb technikai kockázatok a megbízható szegmentálás különböző fényviszonyok mellett, a hasonló alakú és mintázatú darabok megkülönböztetése, valamint a geometriai és képi pontszámok megfelelő kombinálása.

A kiértékelés során külön vizsgálom a kézzel ellenőrzött kontúrokon működő illesztési algoritmust és a teljes képfeldolgozási folyamatot. A fő mérőszámok a helyes első találat aránya, a helyes darab első öt találat közötti megjelenése, a nem létező megoldások felismerése és a keresési idő.

Következő lépésként egy egyszerű, ellenőrizhető prototípust készítek, amelyen először a szegmentálás és a geometriai illesztés működését vizsgálom.
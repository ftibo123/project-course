---
name: FARKAS TIBOR
neptun: DOHOLH
id: 2026-SD-04
github: https://github.com/ftibo123
github_project: https://github.com/ftibo123/project-course/
---

# Kamerás kirakósegéd hiányzó puzzle-darabok kereséséhez

A projekt célja egy telefonról is használható, reszponzív webalkalmazás fejlesztése, amely fényképek alapján segít megtalálni a részben összeállított kirakó egyetlen hiányzó darabját. A felhasználó fényképet készíthet vagy képet tölthet fel a szabad puzzle-darabokról és a kirakóról, kijelölheti az üres helyet, majd a rendszer a darabok alakja, elforgatása és a szomszédos képrészletek folytonossága alapján rangsorolt jelölteket ajánl.

A rendszer képfeldolgozással határolja körül a darabokat, lehetővé teszi a hibás maszkok és kontúrok kézi javítását, valamint kalibrációval egységes síkbeli koordinátarendszerbe hozza a különböző felvételeket. A találatokhoz külön geometriai és képi illeszkedési pontszám tartozik. A megfelelő darab behelyezéséről minden esetben a felhasználó dönt. A projektállapot tartósan menthető, a jóváhagyott behelyezések visszavonhatók.

## Célok

- **Elsődleges cél:** Működő, mobilon használható kirakósegéd készítése, amely egy körülhatárolt belső hiányhoz darab–elforgatás párokat keres és rangsorol.
- **Célfelhasználók / érintettek:** Kirakóval foglalkozó felhasználók, a projekt fejlesztője és a projekt értékelője.
- **Mérhető sikerkritériumok:** A felhasználó létrehozhat és később folytathat egy projektet; a rendszer képes darabokat és célhelyeket feldolgozni, a találatokat rangsorolni, a bizonytalan eredményeket jelezni, valamint a behelyezéseket jóváhagyni és visszavonni. A rangsorolás minőségét külön tesztadatokon mért mutatók igazolják.
- **Korlátok:** Az MVP 24–100 darabos, síkbeli kirakókra, egymást nem fedő szabad darabokra és egyetlen, minden oldalról körülhatárolt belső hiányra összpontosít. A felvételek egyszínű, kontrasztos háttéren, dokumentált körülmények között készülnek. A teljes kirakó automatikus megoldása és az eredeti dobozkép használata nem cél.

## Hatókör

### Benne van a hatókörben

- Kirakóprojektek létrehozása, mentése, megnyitása és folytatása.
- Fényképek készítése telefonon, valamint képek feltöltése.
- A szabad darabok és a részben összeállított kirakó képfeldolgozása.
- Darabazonosítók, eredeti képek, kivágható képrészletek, maszkok és kontúrok tárolása.
- A hibás szegmentálás, maszk és kontúr kézi javítása.
- Az elmosódott, levágott vagy összeérő darabok felismerésének támogatása és ellenőrzési jelzések megjelenítése.
- Perspektíva- és méretarány-korrekció ismert referencia vagy kézzel megadott kalibrációs pontok alapján.
- Egy belső hiányzó célhely kijelölése és szomszédainak azonosítása.
- Darab–elforgatás párok keresése és rangsorolása geometriai és képi illeszkedés alapján.
- A jelöltek kontúr-rávetítésének, pontszámainak és bizonytalanságának megjelenítése.
- Behelyezések jóváhagyása, visszavonása és a darabok foglalásának kezelése.
- Az elavult találatok felismerése és újraszámítása módosítás után.
- Automatizált tesztek, kézzel ellenőrzött mintaadatok és dokumentált kiértékelés.

### Nincs benne a hatókörben

- A teljes kirakó automatikus megoldása.
- A puzzle dobozán található referenciakép kötelező feldolgozása.
- Több hiányzó darab egyidejű, globális optimalizálása.
- Részben nyitott célhelyek és széldarabok általános kezelése.
- Élő kameraképre rajzolt, kiterjesztett valóság alapú jelölések.
- Gépi tanulási modell saját tanítása nagy méretű adatkészleten.
- Többfelhasználós együttműködés és összetett jogosultságkezelés.

## Jegyzetek

A fejlesztés első lépése egy ellenőrizhető prototípus elkészítése, amely mesterséges vagy kézzel előkészített képeken megmutatja a szegmentálást, a kontúrok elforgatását és az alak szerinti rangsorolást. Ezt követi a szomszédos képrészleteket is figyelembe vevő pontozás, a kalibráció, a szerkesztőfelület és a tartós projektmentés.

A képfeldolgozás, a jelöltkeresés és -rangsorolás, valamint a projektállapot kezelése külön komponens legyen. Az eredeti képeket és a kézi javításokat a sikertelen feldolgozás sem törölheti. A geometriai és képi pontszámok rangsorolási értékek, nem igazolt valószínűségek.

A kiértékelésben külön kell választani a kézzel ellenőrzött kontúrokon mért rangsorolási teljesítményt a teljes képfeldolgozási folyamat eredményétől. A tesztkészlet kirakónként váljon el a paraméterhangoláshoz használt adatoktól, hogy a mérés ne legyen megtévesztően kedvező.

# Kamerás kirakósegéd hiányzó puzzle-darabok kereséséhez
Szerző: Farkas Tibor

Neptun: DOHOLH  
Témavezető: Sári Dávid  
Projektazonosító: 2026_SD_04

## Probléma
Egy kirakó hiányzó darabjának megtalálása időigényes lehet, különösen sok hasonló alakú vagy mintázatú darab esetén.
A projekt célja egy mobilon is használható webalkalmazás fejlesztése, amely fényképek alapján megkeresi és rangsorolja a hiányzó helyhez illeszkedő darabokat, figyelembe véve azok alakját, elforgatását és a szomszédos képrészleteket.

## Célfelhasználók
- Kirakóval foglalkozó felhasználók, akik gyorsabban szeretnék megtalálni a hiányzó darabot.
- Mobiltelefonos felhasználók, akik fényképek segítségével keresnének.
- A projekt fejlesztője és értékelője, akik a megoldás működését és pontosságát vizsgálják.

## Tervezett hatókör
A rendszer fő funkciói:
- Projektek létrehozása, mentése és folytatása.
- Puzzle-darabok és a hiányzó hely felismerése képek alapján.
- Felismert kontúrok kézi javítása.
- A perspektíva és a méretarány korrigálása.
- Illeszkedő darabok keresése és rangsorolása geometriai, illetve képi jellemzők alapján.
- Találatok vizuális összehasonlítása, behelyezés jóváhagyása és visszavonása.

Az első változat 24–100 darabos, síkbeli kirakók egyetlen, minden oldalról körülhatárolt belső hiányának megoldására koncentrál. A teljes kirakó automatikus összeállítása nem cél.

## Kezdeti felhasználói utak
1. **Projekt létrehozása:** A felhasználó képeket készít vagy tölt fel a szabad darabokról, amelyeket a rendszer felismer és elkülönít.
2. **Hiányzó hely kijelölése:** A felhasználó megadja a hiány helyét, majd szükség esetén javítja a kontúrokat és a képek geometriáját.
3. **Megfelelő darab keresése:** A rendszer rangsorolja a lehetséges darabokat, a felhasználó pedig megtekinti és jóváhagyja a legjobb találatot.

## Következő lépések
- Képfeldolgozási és kontúrfelismerési prototípus készítése.
- Geometriai illesztés és találatrangsorolás megvalósítása.
- Reszponzív felület és projektmentés kialakítása.
- Az algoritmus tesztelése különböző kirakókon, ellenőrzött adatokkal.

# Blind AI Assistant

**Magyar nyelvű, akadálymentes Android-asszisztens látássérült felhasználók számára**

## A projekt célja

A projekt célja egy olyan Android-alkalmazás prototípusának elkészítése, amely mesterséges intelligencia segítségével támogatja a vak és gyengénlátó felhasználókat rövid, nyomtatott szövegek feldolgozásában.

Az alkalmazás lehetővé teszi, hogy a felhasználó lefényképezzen egy szöveget tartalmazó dokumentumot, például egy meghívót, majd szóban megkérdezze a számára fontos információt. A rendszer a képen található szöveg feldolgozása után magyar nyelvű, hangos választ ad.

A fejlesztés középpontjában az akadálymentes használat, a megbízható válaszadás és a hibás vagy nem megfelelő minőségű képek kezelése áll.

## A megoldandó probléma

A látássérült felhasználók számára nehézséget jelenthet a nyomtatott szövegek önálló elolvasása és az azokban szereplő konkrét információk gyors megtalálása.

A hagyományos szövegfelolvasó megoldások gyakran a teljes szöveg felolvasására összpontosítanak, miközben a felhasználónak sok esetben csak egy meghatározott információra van szüksége.

A projekt egy célzott kérdés-válasz alapú megoldást vizsgál, amelyben a felhasználó megfogalmazhatja, hogy mit szeretne megtudni a lefényképezett szövegből.

**Példafeladat:** a felhasználó lefényképez egy eseménymeghívót, majd megkérdezi: „Mikor kezdődik az esemény?” Az alkalmazás megkeresi a releváns információt, és hangosan közli a választ. Ha a kép nem olvasható, a rendszer jelzi a problémát, és új fénykép készítését javasolja.

## Tervezett működés

1. A felhasználó elindítja az alkalmazást, és lefényképez egy rövid, nyomtatott szöveget.
2. Szóban feltesz egy kérdést a képen szereplő információval kapcsolatban.
3. Az alkalmazás szövegfelismeréssel feldolgozza a képet.
4. A rendszer a felismert szöveg és a felhasználó kérdése alapján megpróbálja meghatározni a választ.
5. Az alkalmazás magyar nyelven, hangosan közli az eredményt.
6. Ha a kép minősége nem megfelelő, vagy a válasz nem állapítható meg kellő biztonsággal, az alkalmazás jelzi a bizonytalanságot, és szükség esetén új fényképet kér.

## A prototípus tervezett funkciói

- **Fényképkészítés:** rövid, nyomtatott szöveget tartalmazó dokumentum rögzítése.
- **Hangalapú kérdésfeltevés:** a felhasználó szóban megfogalmazhatja, milyen információt keres.
- **Optikai karakterfelismerés (OCR):** a képen szereplő szöveg digitális szöveggé alakítása.
- **Kérdésalapú információkinyerés:** a rendszer a felismert szövegből megkeresi a kérdés megválaszolásához szükséges információt.
- **Magyar nyelvű hangos válasz:** a felismert eredmény felolvasása.
- **Hibakezelés:** a nem olvasható kép, a hiányzó információ és a bizonytalan válasz megfelelő kezelése.
- **Újrapróbálkozás:** lehetőség új fénykép készítésére, ha az első feldolgozás nem sikeres.
- **Akadálymentes kezelés:** kompatibilitás az Android TalkBack képernyőolvasójával.
- **Válasz megismétlése:** a korábbi válasz újbóli felolvasása.

A prototípus elsődleges célja nem egy minden élethelyzetben használható általános asszisztens létrehozása, hanem egy jól körülhatárolt feladat megbízható és akadálymentes megvalósítása.

## Kutatási kérdés

**Hogyan befolyásolja a célzott kérdésfeltevés és a hibajavítást segítő visszajelzés a magyar nyelvű, akadálymentes mobilasszisztenssel végzett nyomtatott szövegfeldolgozás megbízhatóságát és feladatvégrehajtását?**

A projekt során különös figyelmet kap annak vizsgálata, hogy a rendszer mennyire pontosan nyeri ki a keresett információt, miként kezeli a rossz minőségű képeket, és mennyire érthetően jelzi a felhasználónak, ha nem tud megbízható választ adni.

## Tervezett technológiák

| Terület | Tervezett technológia vagy megoldás |
|---|---|
| Mobilplatform | Android |
| Programozási nyelv | Kotlin |
| Akadálymentesítés | Android TalkBack és akadálymentes felületi elemek |
| Szövegfelismerés | Meglévő OCR-megoldás |
| Intelligens információkinyerés | Meglévő mesterségesintelligencia-modell vagy API |
| Beszédfelismerés | Androidon elérhető beszédfelismerési megoldás |
| Hangos válasz | Android szövegfelolvasó (Text-to-Speech, TTS) |
| Háttérrendszer | Igény szerint Python és FastAPI |

A konkrét könyvtárak és szolgáltatások kiválasztása a prototípus fejlesztése során, a magyar nyelvi támogatás, az integrálhatóság, a költségek és a felhasználási feltételek figyelembevételével történik.

## Tesztelési és értékelési terv

A prototípus működését előre ellenőrzött, ismert helyes válasszal rendelkező teszteseteken tervezem értékelni.

A kezdeti tesztkészlet tervezett mérete **20–30 eset**, amely többek között az alábbiakat tartalmazza:

- jól olvasható, rövid nyomtatott szövegek;
- gyenge minőségű, elmosódott vagy nehezen olvasható képek;
- olyan szövegek, amelyek csak részben tartalmazzák a keresett információt;
- olyan esetek, amelyekben a kérdésre nem adható megalapozott válasz.

### Tervezett mérőszámok

- **Helyes válaszok aránya:** a helyesen kinyert információk aránya.
- **Hibás válaszok aránya:** a téves vagy a forrásból nem alátámasztható válaszok aránya.
- **Indokolt visszautasítás aránya:** milyen gyakran jelzi megfelelően a rendszer, hogy a rendelkezésre álló információ nem elegendő.
- **Feldolgozási idő:** mennyi idő telik el a kérdés feltevése és a válasz meghallgatása között.
- **Újrafényképezések száma:** milyen gyakran van szükség új kép készítésére.
- **Sikeres feladatvégrehajtás aránya:** milyen arányban jut el a felhasználó a keresett információ megszerzéséig.
- **Akadálymentes használhatóság:** mennyire érthető a kezelési folyamat és a hibákról adott visszajelzés TalkBack használata mellett.

A tesztek során a rendszer technikai pontosságát és a használhatóságot külön szempontként kezelem. Amennyiben lehetőség nyílik rá, a későbbiekben célcsoporthoz tartozó felhasználóktól is gyűjtök visszajelzést, megfelelő tájékoztatás és hozzájárulás mellett.

## A projekt határai

A megvalósíthatóság és az értékelhetőség érdekében az első prototípus az alábbi feladatokra korlátozódik:

- rövid, nyomtatott szövegek feldolgozása;
- a felhasználó konkrét kérdésének megválaszolása;
- magyar nyelvű hangos visszajelzés;
- hibás vagy elégtelen minőségű bemenet kezelése.

Az első változat nem tartalmazza:

- a környezet folyamatos, valós idejű videós elemzését;
- az akadályok felismerését vagy az önálló navigáció támogatását;
- általános, minden tárgyra és élethelyzetre kiterjedő képfelismerést;
- saját mesterségesintelligencia-modell betanítását;
- összetett, egyedi gesztusokra épülő vezérlést.

A kezelési folyamat kialakításánál elsődleges szempont a meglévő Android-akadálymentesítési funkciókkal való együttműködés, nem pedig azok kiváltása.

## Tervezett fejlesztési ütemezés

| Szakasz | Tervezett feladat |
|---|---|
| 1. | A feladat pontosítása, szakirodalom és hasonló alkalmazások áttekintése |
| 2. | Android-projekt létrehozása, alapfelület és TalkBack-kompatibilitás kialakítása |
| 3. | Fényképkészítés és OCR-integráció |
| 4. | Kérdésfeltevés, információkinyerés és hangos válasz megvalósítása |
| 5. | Bizonytalanságkezelés, hibajelzések és újrafényképezési folyamat |
| 6. | Tesztesetek összeállítása, mérés és eredmények kiértékelése |
| 7. | Dokumentáció, bemutató és a szakdolgozat elkészítése |

Az ütemezés a félév során a megvalósítás tapasztalatai és a rendelkezésre álló idő alapján pontosítható.

## Kapcsolódó megoldások és források

A projekt tervezése és értékelése során az alábbi megoldások és kutatási források vizsgálata tervezett:

- [Be My Eyes](https://www.bemyeyes.com/) – látássérült embereket segítő szolgáltatás, amely mesterséges intelligencián alapuló segítséget is kínál.
- [Microsoft Seeing AI](https://www.seeingai.com/) – látássérült felhasználók számára készült, képi információkat és szövegeket feldolgozó alkalmazás.
- [VizWiz-VQA](https://vizwiz.org/) – látássérült felhasználók által készített képeket és azokhoz kapcsolódó kérdéseket tartalmazó kutatási adatforrás.

A kapcsolódó alkalmazások összehasonlítása során a rövid, nyomtatott szövegek feldolgozására, a bizonytalan eredmények kezelésére, az ismételt próbálkozásra és az akadálymentes interakcióra helyezem a hangsúlyt. Külső adatkészlet felhasználása esetén annak licencét és felhasználási feltételeit előzetesen ellenőrzöm.

## Jelenlegi állapot

**Státusz: tervezési és előkészítési szakasz.**

A projekt célja, a kezdeti felhasználási eset és a prototípus tervezett funkciói meghatározásra kerültek. A fejlesztés jelenlegi szakaszában a követelmények pontosítása, a technológiai megoldások kiválasztása és a megvalósítás előkészítése zajlik.

Az Android-alkalmazás működő implementációja még nem készült el. A következő lépés az alapvető Android-projekt létrehozása, majd a fényképkészítés, a szövegfelismerés és a hangos válaszadás fokozatos megvalósítása.

## Várható eredmény

A félév végére egy működő, Androidon bemutatható prototípus elkészítése a cél, amely egy rövid, nyomtatott szövegben szereplő információt a felhasználó kérdése alapján képes megkeresni és magyar nyelven felolvasni.

A prototípus működését dokumentált tesztesetekkel és mérhető eredményekkel tervezem értékelni. A cél annak bemutatása, hogy egy szűk feladatra összpontosító, akadálymentes mobilasszisztens milyen lehetőségeket és korlátokat kínál a látássérült felhasználók támogatásában.

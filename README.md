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
2. A felhasználó szóban feltesz egy kérdést a képen szereplő információval kapcsolatban.
3. Az alkalmazás optikai karakterfelismeréssel (OCR) digitális szöveggé alakítja a képen szereplő tartalmat.
4. A felismert szöveg és a felhasználó kérdése eljut a háttérrendszerhez, amely továbbítja azokat a kiválasztott mesterségesintelligencia-szolgáltatásnak.
5. A rendszer a rendelkezésre álló szöveg alapján megpróbálja meghatározni a választ.
6. Az alkalmazás magyar nyelven, hangosan közli a választ, és lehetőséget biztosít annak megismétlésére.
7. Ha a kép nem olvasható, a keresett információ nem található meg, vagy a válasz nem állapítható meg kellő biztonsággal, az alkalmazás jelzi a problémát, és szükség esetén új fénykép készítését kéri.

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

A prototípus Android-platformra készül, React Native és TypeScript használatával. A háttérrendszer feladata a mobilalkalmazás és a kiválasztott mesterségesintelligencia-szolgáltatás közötti kommunikáció biztosítása.

| Terület | Tervezett technológia vagy megoldás |
|---|---|
| Mobilplatform | Android |
| Mobilalkalmazás | React Native |
| Programozási nyelv | TypeScript |
| Akadálymentesítés | Android TalkBack és akadálymentes felületi elemek |
| Fényképkészítés | React Native-kompatibilis kamera-megoldás |
| Szövegfelismerés (OCR) | Google ML Kit Text Recognition vagy más megfelelő OCR-megoldás |
| Intelligens információkinyerés | Meglévő mesterségesintelligencia-modell API-n keresztül |
| Háttérrendszer | Python és FastAPI |
| Beszédfelismerés | Androidon elérhető, magyar nyelvet támogató beszédfelismerési megoldás |
| Hangos válasz | Android szövegfelolvasó (Text-to-Speech, TTS) |

A mobilalkalmazás felel a felhasználói interakciókért, a fényképkészítésért és a hangos visszajelzésért. A szövegfelismerés lehetőség szerint a mobilkészüléken történik. A háttérrendszer a felismert szöveget és a felhasználó kérdését továbbítja a kiválasztott mesterségesintelligencia-szolgáltatásnak, majd visszaküldi a választ az alkalmazásnak.

A háttérrendszer használatának egyik célja az API-kulcs biztonságos kezelése és az alkalmazás, illetve a mesterségesintelligencia-szolgáltatás közötti kommunikáció elkülönítése. A kezdeti prototípushoz nem tervezek felhasználói fiókokat vagy adatbázist.

A konkrét könyvtárak és szolgáltatások kiválasztása a fejlesztés kezdeti szakaszában, a magyar nyelvi támogatás, az Android-kompatibilitás, az integrálhatóság, a költségek és a felhasználási feltételek figyelembevételével történik. A natív Android-funkciók integrálhatóságát a választott React Native-könyvtárak alapján ellenőrzöm.

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

A tesztelés során külön kezelem a helyes választ, a forrásból nem alátámasztható választ és az indokolt bizonytalansági jelzést. A rendszer nem tekinthető sikeresnek pusztán azért, mert minden kérdésre választ ad: fontos szempont az is, hogy elégtelen vagy hibás bemenet esetén elkerülje a félrevezető válaszokat. A tesztesetekhez előzetesen rögzítem a helyes választ, illetve azt is, ha a rendelkezésre álló információ alapján nem várható megalapozott válasz.

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
| 2. | React Native-projekt létrehozása, Androidon futó alapalkalmazás és TalkBack-kompatibilis felület kialakítása |
| 3. | Fényképkészítés és OCR-integráció megvalósítása, a felismert szöveg ellenőrzése |
| 4. | Python és FastAPI alapú háttérrendszer létrehozása, az alkalmazás és a mesterségesintelligencia-szolgáltatás összekapcsolása |
| 5. | Kérdésfeltevés, információkinyerés és magyar nyelvű hangos válasz megvalósítása |
| 6. | Bizonytalanságkezelés, hibajelzések, válaszismétlés és újrafényképezési folyamat kialakítása |
| 7. | Tesztesetek összeállítása, mérések elvégzése és az eredmények kiértékelése |
| 8. | Dokumentáció, bemutató és a szakdolgozat elkészítése |

A fejlesztés során elsődleges szempont a működő minimális prototípus mielőbbi elkészítése. A további funkciókat erre építve, fokozatosan valósítom meg. Ha valamelyik technológiai elem integrációja a vártnál nehezebbnek bizonyul, a féléves vállalás teljesíthetősége érdekében a legfontosabb funkciókat részesítem előnyben.

## Kapcsolódó megoldások és források

A projekt tervezése és értékelése során az alábbi megoldások és kutatási források vizsgálata tervezett:

- [Be My Eyes](https://www.bemyeyes.com/) – látássérült embereket segítő szolgáltatás, amely mesterséges intelligencián alapuló segítséget is kínál.
- [Microsoft Seeing AI](https://www.seeingai.com/) – látássérült felhasználók számára készült, képi információkat és szövegeket feldolgozó alkalmazás.
- [VizWiz-VQA](https://vizwiz.org/) – látássérült felhasználók által készített képeket és azokhoz kapcsolódó kérdéseket tartalmazó kutatási adatforrás.

A kapcsolódó alkalmazások összehasonlítása során a rövid, nyomtatott szövegek feldolgozására, a bizonytalan eredmények kezelésére, az ismételt próbálkozásra és az akadálymentes interakcióra helyezem a hangsúlyt. Külső adatkészlet felhasználása esetén annak licencét és felhasználási feltételeit előzetesen ellenőrzöm.

## Jelenlegi állapot

**Státusz: tervezési és előkészítési szakasz.**

A projekt célja, a kezdeti felhasználási eset, a tervezett funkciók és az értékelés fő szempontjai meghatározásra kerültek. A fejlesztés előtt álló feladatok közé tartozik a technológiai környezet véglegesítése, a szükséges könyvtárak kipróbálása és a megvalósítás lépéseinek előkészítése.

A működő mobilalkalmazás és a háttérrendszer implementációja még nem készült el. A következő lépés egy Androidon futó React Native-alkalmazás létrehozása, majd a fényképkészítés és a szövegfelismerés megvalósítása. Ezt követően kerül sor a háttérrendszer, a kérdésalapú információkinyerés és a hangos visszajelzés integrálására.

## Várható eredmény

A félév végére egy működő, Androidon bemutatható prototípus elkészítése a cél, amely egy rövid, nyomtatott szövegben szereplő információt a felhasználó kérdése alapján képes megkeresni és magyar nyelven felolvasni.

A prototípus működését dokumentált tesztesetekkel és mérhető eredményekkel tervezem értékelni. A cél annak bemutatása, hogy egy szűk feladatra összpontosító, akadálymentes mobilasszisztens milyen lehetőségeket és korlátokat kínál a látássérült felhasználók támogatásában.

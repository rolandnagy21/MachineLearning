Deep Learning projekt összefoglaló
-----------------------------------
Használt library-k: keras, tensorflow, seaborn, sklearn, matplotlib, cv2, pandas, numpy, glob, random.
Elektromos motorokat (autókhoz) gyártását szimuláló környezetben vagyunk, ahol a gyártósor végén kapott motorokról egy szenzor képet készít. Az automatizált gyártás miatt típushibák keletkeznek: missing cover, missing screw, vagy hibamentes, azaz complete - ezek a dataset label-jei, melyek a class-okat is jelentik, hiszen a motorok hibáinak algoritmizált felismerése klasszifikációs problémát jelent.
A gépi tanulás modellek felépítését teljesen nulláról kezdjük, így először alaposan átvesszük a képi adatok megfelelő betöltését (feature és label vektorok numpy array-ekkel), kezelését (plottolás imshow metódussal, OpenCV resize, cvtColor, képi adatok array-ekben mentésének sajátosságai, reshape), majd ezután jön az első dataset áttekintés, elemzés, class-ok közötti és class-okon belüli különbségek összehasonlítása (ImageGrid-del), illetve a class eloszlás vizsgálata (Pie chart). Ezt követi a különböző modellekkel való klasszifikálás: először a dataset adott modellnek megfelelő formára alakítása (képeket tároló array-ek mérete, 1 dimenzióra laposítás ha szükséges, színes/szürkeárnyalatos képek, stb), majd train és test set-re bontása. A műveletek után kapott eredmények helyességét gyakran tesztelő algoritmusokkal ellenőríztük (quality gate-k). Az első modell a Szupport Vektoros Gépek volt, melynél most Radial Basis Function Kernelt használunk, és erős regularizációt választunk (C paraméter alacsony értéke), valamint trainelésnél (fittelés) a classok-nak gyakoriságukkal inverzen arányos súlyokat adunk meg (balanced sample_weight). A model teljesítményének kiértékelését a teszt adatokon végzett classification report-tal (accuracy), és hőtérképes confusion mátrix-szal végezzük minden modell esetében. 

Robotic Process Automation rövid projekt összefoglaló
-----------------------------------

ML és RPA projektek teljes mappájának elérése
-----------------------------------
A Notebook-ok nagy méretük miatt lassan töltenek be (pull nélkül) és nehezen olvashatóak (cellák outputjai végig ki vannak írva),
az RPA projekt esetében pedig csak a legrelenvásabb kód fileok találhatóak meg itt, ezért    
a 2 projekt teljes mappáját feltölöttem ide:
https://drive.google.com/drive/folders/11qtNoWj1Z9aUZ6ImwchnyAyrsl4fnAXs?usp=sharing
(a ML projekt esetén tartalmazza a DL dataset-t, egyéb fileokat, saját kiegészítéseket (képek, excelek), 
az RPA projekt esetén pedig az VS Solution minden fileját, mint pl. config fileok)


Kiegészítő információk, saját részek a projektekben
-----------------------------------
A Python megvalósítás közben a mélyebb matematikai háttére is fókuszáltak a tanult anyagok, ezeket az elméleti anyagokat (előadásvideók, slideok) kommentbe (saját megfogalmazással) a kódokhoz igazítottam a kódértelmezés közben, annak érdekében, hogy például a hiperparamétereket értően tudjam változtatni, illetve hogy jobban belelássak a kódok mögötti háttérszámításokba. Kiegészítésképp gyakran utánanéztem a használt library-k dokumentációjában az alkalmazott függvények paramétereinek, működésének, ezeket is kommentben fűztem hozzá a kódhoz.

Időnként kódértelmező kommentjeiben szándékosan túl részletesek, vagy nagyon alapvető Python ismeretekhez utalnak vissza, ezzel az volt a cél, hogy ne csak megértsem a hosszabb kódrészleteket, hanem hogy közben tanuljam magamtól történő megírásukat is, és hogy a kommentek ne csak számomra, hanem külső olvasó számára is minél érthetőbbek legyenek.

A tanulási folyamat közben, mikor egy-egy (számomra) összetettebb Code cellához értem, felette hozzáadtam kiegészítő Code cellákat, melyekben a hosszabb kódsorokat részletekre szedve értelmeztem, próbálgattam ki (printelések, stb), így elősegítve a részletek átlátását, hosszabb kódok értő tanulását. Ezeket a hozzáadott kiegészítő cellákat a transzparencia, olvashatóság érdekében mindig a "saját, értelmezéshez" kommenttel kezdtem.

(A Deep Learning képi adatoknál (Google Drive\Python ML projekt\DL for Image Classification\data\top) a Missing Cover ("_MC_") kategóriájú képek felülnézetben félrevezetőek lehetnek, mert bár innen nézve úgy tűnik, hogy rajtuk van a fekete gumi "takaró", oldalsó nézetből már látszik, hogy nem mindegyik részükön van rajta.)

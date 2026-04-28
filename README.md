# garatzaile-jasangarria
# Nire Konpromiso Profesionala: Garatzaile Jasangarriaren Manifestua

**Egilea:** Jonathan Fernandez
**Profila:** Plataforma-anitzetako eta Web Aplikazioen Garatzailea (DAM/PAG)

---

## A. Talde-lanaren auditoria kritikoa: Ikusi gabeko inefizientziak

Gure taldeak garatutako "GameStop Jasangarritasun Plana" dokumentuan, arreta handia eskaini diogu ekonomia zirkularrari (zabor elektronikoaren kudeaketa, kontsolen konponketa) eta datu-zentroen zein denda fisikoen energia berriztagarrien erabilerari. Hala ere, softwarearen arkitekturaren ikuspuntutik, gabezia bat detektatu dut: ez dugu zehaztu nola optimizatuko den garatu dugun ERP aplikazioaren barne-funtzionamendua.

**Zer hobetu liteke?**
GameStop ERP aplikazioak hardware inbentario oso handiak kudeatzen ditu (adibidez, ehunka RAM memoria eta prozesadore). Datu-basearekiko (JDBC) konexioak ez badira efizienteak, zerbitzariaren prozesamendu-karga eta energia-kontsumoa izugarri handitzen dira. Planak "kode optimizatua" aipatzen du, baina ez du neurri teknikorik ematen hau lortzeko.

**Proposamen berritzailea datu teknikoekin:**
* **Datu-baseko kontsulten optimizazioa (Paginazioa):** Bezeroak "Jokoen Katalogoa" irekitzen duenean osagaiak ikusteko, aplikazioak ez lituzke datu-baseko erregistro guztiak aldi berean kargatu behar. Paginazioa eta *PreparedStatement* erabiliz, sareko trafikoa eta zerbitzariaren PUZ kontsumoa zeharo murrizten dira.
* **Cache sistemak inplementatzea:** Askotan aldatzen ez diren datuak (produktuen deskribapenak edo prezioak) memoria-cache batean gordetzea, datu-baseari alferrikako deiak egitea ekidinez.

---

## B. "Green Coding" eta Garapen Jasangarria (SDLC Ikuspegia)

Nire aplikazioen karbono-aztarna murrizteko, honako hiru neurri tekniko hauek aplikatuko ditut garapen-ziklo osoan (SDLC):

1. **Garatze eta Diseinu Fasea (Interfaze arinak):**
   Java Swing bidezko interfazeetan (adibidez, saioa hasteko pantailan), elementu grafikoen karga optimizatuko dut. Memoria-ihesak (*memory leaks*) prebenituko ditut objektuak behar bezala suntsituz eta *Garbage Collector*-ari lana erraztuz, bezeroaren ordenagailuak energia gutxiago gastatu dezan.
   
2. **Inplementazio Fasea (Hosting Berdea):**
   Gure planak hodei-konputazio eraginkorra aipatzen duenez, nire ERP-aren datu-basea energia %100 berriztagarria erabiltzen duten zerbitzarietan (*Green Hosting*) hedatuko dut. Baliabideak soilik erabiltzaileak konektatzen direnean kontsumituko dituzten arkitekturak lehenetsiko ditut.

3. **Mantenamendu Fasea (Errendimenduaren monitorizazioa):**
   CI/CD pipeline-etan errendimendu-test automatizatuak sartuko ditut. Kode berri batek (adibidez, bezero berri bat erregistratzeko funtzioak) datu-basean itxaron-denbora gehiegi eskatzen badu, automatikoki blokeatuko da produkziora joan aurretik, karbono-aztarna handitzea ekidinez.

---

## C. Nire ibilbide-orri etikoa: Aldaketarako eragilea

Laster praktikak egingo ditudan enpresan (**Exel Eventos**), ez naiz kode-idazle huts bat izango; teknologiaren inpaktu sozial eta ingurumenekoaren ikuspuntu sistemikoa duen profesional bat baizik.

**Nire lehenengo ekintza zehatza:**
Exel Eventos-en esleitzen didaten lehenengo proiektuan, Irisgarritasun Digitala (A11y) nire kodearen estandar bihurtuko dut. Garatzen dudan edozein interfaze edo webgunek teklatu bidezko nabigazioa ahalbidetuko du eta pantaila-irakurleentzat egokituta egongo da. Horrez gain, enpresako nire tutoreari kodearen optimizazioaren inguruko praktika onak (GameStop proiektuan ikasitakoak) aplikatzea proposatuko diot, enpresaren baliabide digitalak efizienteagoak izan daitezen.

**Nola eragingo du nire lanak gizartean eta ingurumenean modu positiboan?**
* **Gizarte mailan:** Inklusio digitala bermatuko dut nire praktiketan. Irisgarritasun-arauak betetzen dituen aplikazio batek pertsona guztiei berdintasunez parte hartzeko aukera ematen die, edozein direla ere haien gaitasunak.
* **Ingurumen mailan:** Kode garbi eta optimizatu batek hardwarearen baliabide gutxiago eskatzen ditu. Horri esker, bezeroek eta erabiltzaileek gailu zaharrekin lanean jarraitu dezakete errendimendua galdu gabe, hardware berriaren beharra atzeratuz eta zabor elektronikoa (e-waste) murriztuz.

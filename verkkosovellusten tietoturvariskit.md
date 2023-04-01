


 Harjoituksen tarkoituksena on tutustua eri verkkosovellusten tietoturvariskeihin hyödyntäen OWASP WebGoat-palvelinta.
 
### Laitteisto
 
* Käyttöjärjestelmä	Microsoft Windows 10 Enterprise LTSC 64 bit
* Prosessori i5-6600
* RAM 16 GB
* Virtuaaliohjelmisto : Oracle VM VirtualBox
* Virtuaalikoneen prosessori: i5-6600K CPU @ 3.50GHz
* Virtuaalikoneen käyttöjärjestelmä: Ubuntu 21.10 (64-bit)
* Virtuaalikoneen RAM : 4 GB





## Injection - SQL-injection

SQL-injektio on hyökkäys, missä vahingollista koodia saadaan syötettyä tietokantaan erillaisten asiakasohjelmien kautta ja hyökkäjä pääsee sellaisiin tietoihin käsiksi, mihin hänellä ei ole oikeuksia. SQL-hyökkäykset ovat suuri riski datan eheydelle ja turvallisuudelle.

Harjoitushyökkäyksien aikana onnistuin pääsemään dataan käsiksi hyödyntämällä erillaisia SQL-kielen ominaisuuksia esimerkiksi käyttäen:

     ' OR '1'=1
     
Komentoa, joka evaluoi kaiken todeksi välittämättä siitä, mitä sitä ennen oli syötetty.
 
Toinen komento minkä avulla hyökkäys onnistui oli ketjuttamalla erillaisia kyselyitä (Query chaining) esimerkiksi syöttämällä:

     '; UPDATE tablename
    
 Minkä avulla pääsi muokkaamaan taulukkoa.
 
 SQL-injektio hyökkäys oli mahdollista, sillä käyttäjällä oli suora pääsy tietokantaan ja erillaisten SQL-kielen metamerkkien, kuten " -- , ' , ja ; " syöttäminen syötekenttään oli mahdollista.
 
 
 SQL-hyökkäyksiä vastaan voi puolustautua esimerkiksi kieltämällä erillaisten symbolien syöttämisen syötekenttään. Parametrisoidut komennot taas luovat SQL-kyselyn etukäteen, mikä estää uusien SQL-kyselyiden luomisen ja jonka seurauksena hyökkääjä ei voi lisätä uusia komentoja syötteessen. Kolmas tapa estää SQL-hyökkäyksiä on tiedon hajauttaminen ja käyttäjän oikeuksien tarkka määrittäminen.
 
 
 ![image](https://user-images.githubusercontent.com/106889187/229304298-3239a758-829d-4214-90f2-c9e863b5b52d.png)
 
## Broken Authentication - Authentication Bypasses

Authentication bypasses hyökkäyksissä tarkoituksena ohittaa erillaiset varmenteet kirjautumisessa yleensä hyödyntämällä virhettä konfiguraatiossa tai logiikassa.


Hyökkäyksessä oli tarkoitus ohittaa kaksi turvakysymystä. Käytin hyödyksi OWASP ZAP välityspalvelinta ja ennenkuin painoin kirjautumista niin keskeytin nettisivulta tulevat pyynnöt. Kun painoin kirjautumista, niin pääsin tarkastelemaan uutta pyyntöä, ilman että se menisi eteenpäin ja toteutuisi vääräksi. Muutin pyynnön parametrejä lisäämällä niihin uusia merkkejä, jonka seurauksena kysymykset ohitettiin.

Hyökkäys onnistui, sillä aplikaatiossa oli annettu lupa käyttäjän muokata pyyntöjä, ennen niiden lähettämistä eteenpäin. Varmenneprotokolla ei saisi olla esillä ja saatavilla asiakaspuolen verkkoselaimen komentosarjassa ja käyttäjän antama syöte tulisi tarkistaa palvelimen puolella.

![image](https://user-images.githubusercontent.com/106889187/229314122-c52e39b1-65bf-4b17-99d1-a7b5d09de55d.png)


## Sensitive Data Exposure - Insecure Login

Herkän ja salaamattoman datan vuotaminen toteutuu jos dataa ei siirtäessä tai varastoidessa salata eri menetelmillä.

Hyökkäyksen tarkoitus oli saada selvillä käyttäjän kirjautumistietoja pakettianalysaattorin avulla. Lähettämällä tyhjän kirjautumispyynön pääsin tarkastelemaan pyynnön tietoja ja löysin toisen käyttäjän kirjautumistiedot salaamattomina. 

Hyökkäys onnistui, koska herkkää dataa ei oltu salattu ja suojattu.

Hyökkäys voitaisiin estää käyttämällä HTTPS protokollaa ja varmistamalla, että kaikki data on suojattua. Salasanat myös pitäisi suojata  suolatuilla hajautusalgoritmeillä.


![image](https://user-images.githubusercontent.com/106889187/229315477-ccbd9e32-28ce-404f-8947-21f0b679d586.png)





 ## Lopuksi 
 
 Tässä harjoituksessa tutustuin erillaisiin verkkosovellusten tietoturvariskeihin.
 
 
## Lähteet

Kurssin tietoturvan perusteet - ICI002AS2A-3006 luentokalvot

OWASP (https://owasp.org/)


Mikä on SQL injection -hyökkäys?, Laura Klusaitė - 09.03.2023 (https://nordvpn.com/fi/blog/sql-injektio/)


#### Tehnyt Roi Partanen (1.4.2023)

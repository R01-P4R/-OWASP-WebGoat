


 Harjoituksen tarkoituksena on tutustua eri verkkosovellusten tietoturvariskeihin hyödyntäen OWASP WebGoat-palvelinta.
 
### Laitteisto
 
* Käyttöjärjestelmä	Microsoft Windows 10 Enterprise LTSC 64 bit
* Prosessori i5-6600
* RAM 16 GB
* Virtuaaliohjelmisto : Oracle VM VirtualBox
* Virtuaalikoneen prosessori: i5-6600K CPU @ 3.50GHz
* Virtuaalikoneen käyttöjärjestelmä: Ubuntu 21.10 (64-bit)
* Virtuaalikoneen RAM : 4 GB





## SQL-injektio hyökkäys 

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




 ## Lopuksi 
 
 Tässä harjoituksessa harjoittelin uusien komentojen luontia Bahilla ja Pythonilla.
 
 
## Lähteet

Linux Palvelimet 2023 alkukevät, Tero Karvinen (https://terokarvinen.com/2023/linux-palvelimet-2023-alkukevat/)

30 Bash Script Examples, Fahmida Yesmin - 2018 (https://linuxhint.com/30_bash_script_examples/)


#### Tehnyt Roi Partanen (13.3.2023)

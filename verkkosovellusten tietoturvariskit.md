
# H14

 Harjoituksen tarkoituksena on luoda uusia komentoja käytten Bashia ja Pythonia(3).
 
### Laitteisto
 
* Käyttöjärjestelmä	Microsoft Windows 10 Enterprise LTSC 64 bit
* Prosessori i5-6600
* RAM 16 GB
* Virtuaaliohjelmisto : Oracle VM VirtualBox
* Virtuaalikoneen prosessori: i5-6600K CPU @ 3.50GHz
* Virtuaalikoneen käyttöjärjestelmä: Ubuntu 21.10 (64-bit)






## Komento Bashilla (11:16)

Luodaan komento, joka tervehtii käyttäjää tämän syöttämän nimen perusteella. 

Aloitin harjoituksen siirtymällä aikaisemmin luotoon kansion 'scripting', komennolla:

    $ cd scripting/
  
Loin uuden tiedoston käyttäen micro-editoria komennolla:

    $ micro inputname
    
 Ja lisäsin sen sisälle:
 
 ![image](https://user-images.githubusercontent.com/106889187/224656708-ee4dc0ed-60dc-45b3-a33f-fdcfed2a0479.png)

Kokeilin, että ohjelma toimii komennolla:

      $ bash inputname
      
      
  ![image](https://user-images.githubusercontent.com/106889187/224658212-3375755d-0ed8-47e9-89c2-20bf0e336674.png)
 
     
 Ohjelma toimii.
 
 
 Seuraavaksi katsoin, mitkä oikeudet ohjelmalla oli käyttäen komentoa:
 
    $ ls -l inputname
 
![image](https://user-images.githubusercontent.com/106889187/224658571-21c4a8d9-fcbb-4a0e-b1c5-3296eb7cb1f2.png)


Muokkasin oikeuksia niin, että kaikilla ryhmillä oli oikeus suorittaa ohjelmaa komennolla:

      $ sudo chmod ugo+x inputname

Kopioin vielä ohjelman kansioon '/usr/local/bin', jotta ohjelman voi suorittaa kuten muutkin bash-komennot, käyttäen komentoa:

    $ sudo cp inputname /usr/local/bin


![image](https://user-images.githubusercontent.com/106889187/224660229-084279b7-0c75-4a04-8f6d-1a68d4d1a27c.png)

  Komennon ajaminen onnistui ilman bash-etuliitettä.

![image](https://user-images.githubusercontent.com/106889187/224660868-6ac56bda-2ef9-42f8-a79f-e824f368b66a.png)


Loin vielä uuden käyttäjän komennolla:

    $ sudo adduser testeri
    
  Kokeilin ajaa uuden komennon uudella käyttäjällä ja ohjelma toimi odotetusti.
  
  ![image](https://user-images.githubusercontent.com/106889187/224662115-3cb71935-5b49-4b99-8842-2f9202255b84.png)

  

## Komento Python3:lla (11:34)

Luodaan komento, joka kertoo kellonajan ja päivämäärän käyttäen Pythonia.

Aloitin luomalla tiedoston komennolla:

    $ micro aika
    
    
 Lisäsin tiedoston sisälle seuraavan koodin:
 
![image](https://user-images.githubusercontent.com/106889187/224669318-34fd1e7b-a581-4229-90d2-0264f879314d.png)


Kokeilin ajaa komennon ja ohjelma toimi.


![image](https://user-images.githubusercontent.com/106889187/224669041-e8583b66-f8b7-4041-a909-8684730117d3.png)


Seuraavaksi tarkistin ohjelman oikeudet komennolla:

    $ ls -l aika

ja päivitin suoritusoikeudet komennolla:

    $ sudo chmod ugo+x aika

![image](https://user-images.githubusercontent.com/106889187/224670052-b779bec4-050e-49d3-b2ce-c7bbe187161a.png)

![image](https://user-images.githubusercontent.com/106889187/224670218-d6e1cbe7-c28d-4eaf-af95-bd260f388904.png)


Sitten kopion ohjelman kansioon '/usr/local/bin', jotta ohjelman voi suorittaa kuten muutkin bash-komennot, käyttäen komentoa:

    $ sudo cp aika /usr/local/bin

![image](https://user-images.githubusercontent.com/106889187/224670732-3754859c-3cc8-42aa-8249-ab9841c0645f.png)

Testasin vielä toisella käyttäjällä ja ohjelma toimi odotetusti.

![image](https://user-images.githubusercontent.com/106889187/224671146-23932a0a-5b80-450e-9a55-0fffa8a49259.png)

## Bash-komento monelle tiedostolle (12:33)

Luodaan bash-komento, joka listaa tiedostot ja niiden sisällön.

Aloitin luomalla tiedoston komennolla:

    $ micro filut
    
Ja lisäsin sen sisälle:

![image](https://user-images.githubusercontent.com/106889187/224691363-428312bf-f474-4760-80c1-c210e9036f54.png)

Testasin ohjelman toimivuutta komennolla:

    $ bash filut
    
![image](https://user-images.githubusercontent.com/106889187/224691617-34fc1197-e348-4405-b329-ec69b426631d.png)

Ja ohjelma listasi tiedostot ja niiden sisällön.


Seuraavaksi päivitin ohjelman suoritusoikeudet ja tallensin sen kansioon '/usr/local/bin', käyttäen komentoja:

    $ sudo chmod ugo+x filut
    $ sudo cp filut /usr/local/bin

Lopuksi testasin eri käyttäjillä tomiiko ohjelma.

![image](https://user-images.githubusercontent.com/106889187/224692862-ac3139db-fad8-4d5e-8c58-658a9aa7ae1a.png)

![image](https://user-images.githubusercontent.com/106889187/224693298-570659f9-ebb7-4ea7-ace6-5ef91f4da762.png)

![image](https://user-images.githubusercontent.com/106889187/224693626-20eaa833-cefe-47f4-b1d7-921cd484ba9d.png)

Ohjelma toimi odotetusti kaikilla käyttäjillä.


 ## Lopuksi 
 
 Tässä harjoituksessa harjoittelin uusien komentojen luontia Bahilla ja Pythonilla.
 
 
## Lähteet

Linux Palvelimet 2023 alkukevät, Tero Karvinen (https://terokarvinen.com/2023/linux-palvelimet-2023-alkukevat/)

30 Bash Script Examples, Fahmida Yesmin - 2018 (https://linuxhint.com/30_bash_script_examples/)


#### Tehnyt Roi Partanen (13.3.2023)

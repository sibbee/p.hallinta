# h6 Windows  

## x) Lue ja tiivistä  

Halonen, Rajala ja Ollikainen 2023: [Installing Windows 10 on a virtual machine](https://github.com/therealhalonen/PhishSticks/blob/master/notes/ollikainen/windows.md)  

Ohjeessa näytetään vaihe vaiheelta Windows 10 -käyttöjärjestelmän asentaminen virtuaalikoneelle  
= Lataa ISO-tiedosto ja lisää se VirtualBoxiin. Aseta koneen resurssit ja käynnistä kone.  


LSB Workgroup, The Linux Foundation 2015: [Filesystem Hierarchy Standard](https://refspecs.linuxfoundation.org/FHS_3.0/fhs/index.html)  

FHS eli Filesystem Hierarchy Standard on:  
- Standardi. joka määrittelee Linuxin tiedostojärjestelmän hierarkisen rakenteen.  
- Mitä kansioita & niiden käyttötarkoitus  

Muun muassa:  

/etc sisältää konfiguraatiotiedostot ja -hakemistot  
/home kansiossa käyttäjien henkilökohtaiset kotihakemistot  
/srv kansio on palveluiden tiedostojen ja tietojen tallentamiseen esim. web  
/usr sisältö on usein jaettua, esim. asennetut ohjelmat, kirjastot yms jaetut resurssit  


## a) Asenna Windows virtuaalikoneeseen  

Windowsin asennuksen suoritin [Halosen, Rajalan ja Ollikaisen ohjeen](https://github.com/therealhalonen/PhishSticks/blob/master/notes/ollikainen/windows.md) mukaisesti.  
Tämä tehtiin luennolla, joten kuvia tästä huikeasta osuudesta ei valitettavasti ole.  

![image](https://github.com/sibbee/p.hallinta/assets/149330317/a5a61a73-eb7b-4437-a51d-21d21e58bf24)  

Yleisnäkymä virtuaalikoneesta asennuksen ja määrittelyn jälkeen  


## b) Asenna Salt Windowsille  

Ensimmäiseksi tarvitsen asennustiedoston ja sen sain virtuaalikoneen selaimella sivustolta [Windows - Salt install guide](https://docs.saltproject.io/salt/install-guide/en/latest/topics/install-by-operating-system/windows.html)  

![image](https://github.com/sibbee/p.hallinta/assets/149330317/eb129f20-8e30-4ac4-95be-4c6090a1aaf9)  

Valitsin kuvan version, lataus tapahtui hyvin nopeasti  

![image](https://github.com/sibbee/p.hallinta/assets/149330317/f2ef12ca-3221-4995-9eba-a5066f6f23fc)  

Nextillä eteenpäin, asetin koneeni IP-osoitteen vaadittuun kohtaan.  
Kun asennusprosessi (joka myös tapahtui nopeasti) suoriutui, tarkastin asennuksen ```salt-call --local``` komennolla:  
(Tero Karvinen, [Infra as Code 2023](https://terokarvinen.com/2023/configuration-management-2023-autumn/))  

![image](https://github.com/sibbee/p.hallinta/assets/149330317/78520f7b-8738-49a2-bfa8-f7bda7ca1761)  

![image](https://github.com/sibbee/p.hallinta/assets/149330317/fd725c8e-2625-4f59-bb13-71f2a3288e1d)  

Saltin asennus onnistui. Jipii  


## c) Kerää Windows-koneesta tietoa  

Tässä kohdassa apuna [Tero Karvisen artikkeli](https://terokarvinen.com/2023/salt-vagrant/#infra-as-code---your-wishes-as-a-text-file) (2023)  

Tähän käytin komentoa ```salt-call --local grains.item``` ja perään kaikkia kivoja juttuja mitä muistelin aikaisemmissa raporteissa osoittaneeni  

![image](https://github.com/sibbee/p.hallinta/assets/149330317/75855fc8-6a54-4675-87b1-1cda60eac707)  

cpu_model eli prosessorimalli on toki sama joka raudalla  
cpuarch eli prossun arkkitehtuuri AMD64  
ip osoite  
muistin määrä ohjeen mukaan  
prosessorien määrä ohjeen mukaan (voi parantaa suorituskykyä jos sitä vaativa työkuorma)  
sekä käyttöjärjestelmä  

## d) Kokeile Saltin file -toimintoa Windowsilla  

Tässä tehtävässä loin kuvan polkuun tiedoston, joka ilmestyi työpöydälleni  

![image](https://github.com/sibbee/p.hallinta/assets/149330317/d93ac82c-3172-4300-a508-fcbab5e0f74e)  

Kirjoitin tiedoston sisälle runon ja shellissä luin sisällön ```cat tiedosto.txt``` komennolla  

![image](https://github.com/sibbee/p.hallinta/assets/149330317/666f1627-3dc5-4c62-9f8b-6bd48308c59d)  


## e) Kokeile jotain itsellesi uutta toimintoa Saltista  

Testasin komentoa ```salt-call --local cmd.run 'systeminfo'```, joka toimi ja sain pitkän listan tietoa:   

![image](https://github.com/sibbee/p.hallinta/assets/149330317/e6b2805c-b4b8-4755-92d1-9336b07b3471)  

## Lähteet  

Tero Karvinen 2023. Infra as Code 2023. Luettavissa: https://terokarvinen.com/2023/configuration-management-2023-autumn/  
Tero Karvinen 2018. Control Windows with Salt. Luettavissa: https://terokarvinen.com/2018/04/18/control-windows-with-salt/ Luettu: 3.12.2023  
Tero Karvinen 2023. Salt Vagrant - automatically provision one master and two slaves. Luettavissa: https://terokarvinen.com/2023/salt-vagrant/#infra-as-code---your-wishes-as-a-text-file Luettu: 3.12.2023  

Halonen, Rajala ja Ollikainen 2023: Installing Windows 10 on a virtual machine. Luettavissa: https://github.com/therealhalonen/PhishSticks/blob/master/notes/ollikainen/windows.md Luettu: 3.12.2023  

Linuxfoundation.org 2015. Filesystem Hierarchy Standard. Luettavissa: https://refspecs.linuxfoundation.org/FHS_3.0/fhs/index.html Luettu: 4.12.2023  

Saltproject. Windows - Salt install guide. Luettavissa: https://docs.saltproject.io/salt/install-guide/en/latest/topics/install-by-operating-system/windows.html Luettu: 3.12.2023  






# h6 Windows  

## x) Lue ja tiivistä  

Halonen, Rajala ja Ollikainen 2023: [Installing Windows 10 on a virtual machine](https://github.com/therealhalonen/PhishSticks/blob/master/notes/ollikainen/windows.md)  

Ohjeessa näytetään vaihe vaiheelta Windows 10 -käyttöjärjestelmän asentaminen virtuaalikoneelle  
LTSC = long term servicing channel eli pidempi tuki  
RAM ainakin 8GB  




## a) Asenna Windows virtuaalikoneeseen  

Windowsin asennuksen suoritin [Halosen, Rajalan ja Ollikaisen ohjeen](https://github.com/therealhalonen/PhishSticks/blob/master/notes/ollikainen/windows.md) mukaisesti.  

![image](https://github.com/sibbee/p.hallinta/assets/149330317/a5a61a73-eb7b-4437-a51d-21d21e58bf24)  

Yleisnäkymä virtuaalikoneesta  


## b) Asenna Salt Windowsille  

Ensimmäiseksi tarvitsen asennustiedoston ja sen sain sivustolta [Windows - Salt install guide](https://docs.saltproject.io/salt/install-guide/en/latest/topics/install-by-operating-system/windows.html)  

![image](https://github.com/sibbee/p.hallinta/assets/149330317/eb129f20-8e30-4ac4-95be-4c6090a1aaf9)  

Valitsin kuvan version, lataus tapahtui hyvin nopeasti  

![image](https://github.com/sibbee/p.hallinta/assets/149330317/f2ef12ca-3221-4995-9eba-a5066f6f23fc)  

Nextillä eteenpäin, asetin koneeni IP-osoitteen vaadittuun kohtaan.  
Kun asennusprosessi (joka myös tapahtui nopeasti) suoriutui, tarkastin asennuksen ```salt-call --local``` komennolla:  

![image](https://github.com/sibbee/p.hallinta/assets/149330317/78520f7b-8738-49a2-bfa8-f7bda7ca1761)  

![image](https://github.com/sibbee/p.hallinta/assets/149330317/fd725c8e-2625-4f59-bb13-71f2a3288e1d)  

Saltin asennus onnistui.  


## c) Kerää Windows-koneesta tietoa  

Tässä kohdassa apuna [Tero Karvisen artikkeli](https://terokarvinen.com/2023/salt-vagrant/#infra-as-code---your-wishes-as-a-text-file) (2023)  

Tähän käytin komentoa ```salt-call --local grains.item``` ja perään kaikkia kivoja juttuja mitä muistelin  

![image](https://github.com/sibbee/p.hallinta/assets/149330317/75855fc8-6a54-4675-87b1-1cda60eac707)  


## d) Kokeile Saltin file -toimintoa Windowsilla  

Tässä tehtävässä loin kuvan polkuun tiedoston, joka ilmestyi työpöydälleni  

![image](https://github.com/sibbee/p.hallinta/assets/149330317/d93ac82c-3172-4300-a508-fcbab5e0f74e)  

Kirjoitin tiedoston sisälle ja shellissä luin sisällön ```cat tiedosto.txt``` komennolla  

![image](https://github.com/sibbee/p.hallinta/assets/149330317/666f1627-3dc5-4c62-9f8b-6bd48308c59d)  



## e) Kokeile jotain itsellesi uutta toimintoa Saltista  

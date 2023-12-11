## h7 / Miniprojekti  

Tämä miniprojekti on osa Tero Karvisen [Palvelinten Hallinta](https://terokarvinen.com/2023/configuration-management-2023-autumn/) -kurssia.  
Tässä projektissa tavoittenani on luoda moduuli, joka sisältää vähän kaikkea tähän mennessä kurssilla opiskeltua.  

Poistin edelliset virtuaalikoneet komennolla ```vagrant destroy``` ja asensin uudet [Tero Karvisen ohjeiden](https://terokarvinen.com/2023/salt-vagrant/#infra-as-code---your-wishes-as-a-text-file) mukaisesti.  
Uudet virtuaalikoneet noudattavat myös herra-orja arkkitehtuuria, käytössäni yksi herra ja kaksi minionia.  

Loin ensiksi polkuun /srv/salt apache2 kansion asennusta varten. Haluan myös omat kotisivut.  
Tilatiedoston komento löytyy Tero Karvisen [ohjeista](https://terokarvinen.com/2018/04/03/apache-user-homepages-automatically-salt-package-file-service-example/)  

![image](https://github.com/sibbee/p.hallinta/assets/149330317/c8d37385-ed70-4017-a150-1c76e158a8ef)  

![image](https://github.com/sibbee/p.hallinta/assets/149330317/1ab1eb0d-8afd-45a9-8957-e85d083bee7e)  

Ajoin tämän t001 koneella.  

![image](https://github.com/sibbee/p.hallinta/assets/149330317/edcea6b1-e34a-4644-a30a-4f583f010759)  

Kotisivuni ulkoasu on hieman vaiheessa.  

![image](https://github.com/sibbee/p.hallinta/assets/149330317/2152dd66-679c-43b0-99c3-5974abad3fd3)  

Tämän jälkeen ajattelin että muutamien erilaisten scriptien kirjottaminen olisi kivaa.  
Tässä näkyy loruja.sh joka ajettaessa näyttää päivämäärän ja erinäisiä tietoja virtuaalikoneesta.  

![image](https://github.com/sibbee/p.hallinta/assets/149330317/17babdf2-0d38-4580-83a9-67976a9716e4)  

## Lähteet:  

Tero Karvinen 2023. Salt Vagrant - automatically provision one master and two slaves. Luettavissa: https://terokarvinen.com/2023/salt-vagrant/#infra-as-code---your-wishes-as-a-text-file  
Tero Karvinen 2023. Apache User Homepages Automatically. Luettavissa: homepages-automatically-salt-package-file-service-example/  










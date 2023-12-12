# h7 / Miniprojekti  

Tämä miniprojekti on osa Tero Karvisen [Palvelinten Hallinta](https://terokarvinen.com/2023/configuration-management-2023-autumn/) -kurssia.    

Poistin edelliset virtuaalikoneet komennolla ```vagrant destroy``` ja asensin uudet [Tero Karvisen ohjeiden](https://terokarvinen.com/2023/salt-vagrant/#infra-as-code---your-wishes-as-a-text-file) mukaisesti.  
Uudet virtuaalikoneet noudattavat myös herra-orja arkkitehtuuria, käytössäni yksi herra ja kaksi minionia.  

## Apache
Loin ensiksi polkuun /srv/salt apache2 kansion asennusta varten. Haluan myös omat kotisivut.  
Tilatiedoston komento löytyy Tero Karvisen [ohjeista](https://terokarvinen.com/2018/04/03/apache-user-homepages-automatically-salt-package-file-service-example/)  
(Aluksi ei toiminut, unohdin "name" jälkeen kaksoispisteen)

![image](https://github.com/sibbee/p.hallinta/assets/149330317/c8d37385-ed70-4017-a150-1c76e158a8ef)  

![image](https://github.com/sibbee/p.hallinta/assets/149330317/1ab1eb0d-8afd-45a9-8957-e85d083bee7e)  

Ajoin tämän vain toiselle minionille t001 komennolla ```sudo salt 't001' state.apply apache2```.  
Tätä ennen ilmeni virheilmoitus: 
_Release file for ... is not valid yet (invalid for another 10h 35min 28s). Updates for this repository will not be applied._ josta hämmennyin kovasti. 

Keskustelu [Redditissä](https://askubuntu.com/questions/1096930/sudo-apt-update-error-release-file-is-not-yet-valid) & muut apusivut ohjeistivat päivittämään aikavyöhykkeen (toden totta, toinen minioni näytti eilisiltaa ja herra myös jäljessä) 
Tästä ei valitettavasti kuvaa, koitin paria eri komentoa mutta lopulta tuhosin vain koneen ja loin uuden. 

Epäilen ongelman syyksi mahdollista sleep modea 

![image](https://github.com/sibbee/p.hallinta/assets/149330317/edcea6b1-e34a-4644-a30a-4f583f010759)  

Yhteenveto ja kotisivuni ulkoasu.  

![image](https://github.com/sibbee/p.hallinta/assets/149330317/2152dd66-679c-43b0-99c3-5974abad3fd3)  

## Loruja.sh

Tämän jälkeen scriptin kirjoittamista.  
Tässä näkyy loruja.sh, jonka kirjoitin näyttämään mm. päivämäärän ja erinäisiä tietoja virtuaalikoneesta.  
Echojen määrä aiheutti pientä päänsärkyä.. ilmeisesti ei muuta tapaa saada tyhjää väliä? 

![image](https://github.com/sibbee/p.hallinta/assets/149330317/9cf4305f-53de-4c66-9ab4-8916c2171375)  

## Ohjelmapaketti 

Kirjoitin tilatiedoston joka asentaa erilaisia ohjelmia 

![image](https://github.com/sibbee/p.hallinta/assets/149330317/c7d4cad2-0b5a-4cf6-866e-30fe0d234858)

Tämä kohta ei ollut kovin kummoinen. Kertaus tekee kuitenkin aina hyvää. 


![image](https://github.com/sibbee/p.hallinta/assets/149330317/c8b9d572-c3bc-4590-badc-5954d2915217) 

## Mato ja käärme 

Komento ```sudo apt-get install bsdgames``` asensi pelipaketin. 

Kirjoittamalla "snake" avasi kummallisen pelin jossa minua jahdattiin. 

![image](https://github.com/sibbee/p.hallinta/assets/149330317/978971d9-09ab-4d4c-8a1e-8af7d939e565) 

Testasin huviksi sanaa "worm" joka avasi perinteisen matopelin, kontrolli numpadilla/nuolinäppäimillä. 

![image](https://github.com/sibbee/p.hallinta/assets/149330317/a13d38aa-a1f5-4b4b-b674-93cac8f64c9d) 

 

## Lähteet:  

Tero Karvinen 2023. Salt Vagrant - automatically provision one master and two slaves. Luettavissa: https://terokarvinen.com/2023/salt-vagrant/#infra-as-code---your-wishes-as-a-text-file  
Tero Karvinen 2023. Apache User Homepages Automatically. Luettavissa: homepages-automatically-salt-package-file-service-example/  

2DayGeek.com. Bash Script to View System Information on Linux. Luettavissa: https://www.2daygeek.com/bash-shell-script-view-linux-system-information/  

AskUbuntu. sudo apt update error: "Release file is not yet valid". Luettavissa: https://askubuntu.com/questions/1096930/sudo-apt-update-error-release-file-is-not-yet-valid 

AskUbuntu. How to play snake in terminal? Luettavissa: https://askubuntu.com/questions/376558/how-to-play-snake-in-terminal 

Siiri Katilainen 2023. h4 Demonit. Luettavissa: https://github.com/sibbee/p.hallinta/blob/main/h4/Demonit.md 

OpenAI ChatGPT. How can I view system information bash script 

Machine clock loses time synchronisation when computer goes to sleep. Luettavissa: https://github.com/laravel/homestead/issues/799 











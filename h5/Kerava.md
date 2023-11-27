# CSI Kerava  

## x) Lue ja tiivistä  

Tero Karvisen [artikkelin](https://terokarvinen.com/2018/04/03/apache-user-homepages-automatically-salt-package-file-service-example/) tiivistys:  

Artikkelissa ohjeistetaan miten Saltilla luodaan Apachessa automaattisesti käyttäjän kotisivut.  
Asenna ensin kaikki manuaalisesti.  
Selvitä, mitä määritystiedostoja on muokattu; sudolla tehdyt muokkaukset ilmiselviä  
Idempotentit komennot tiloihin  
Ongelmatilanteissa mm. oikeuksien tarkastaminen  

## a) CSI Kerava  
Näytä 'find' avulla viimeisimmäksi muokatut tiedostot /etc/-hakemistosta ja kotihakemistostasi. Selitä kaikki käyttämäsi parametrit ja format string 'man find' avulla.  

Eli siis komennolla ```$ sudo find -printf "%T+ %p\n" | sort -r | head``` näytän viimeisimmät tapahtumat  

Ensiksi /etc/ kansiosta:  

![image](https://github.com/sibbee/p.hallinta/assets/149330317/32646391-5ea7-41bf-9d3f-1b267d4a3bfb)  

Siellä näkyy tiedosto muokkaus.txt jonka loin aikaisemmin ja testasin näkyykö  
Sekä vielä kotihakemistosta:  

![image](https://github.com/sibbee/p.hallinta/assets/149330317/be6e6480-bfe3-4338-8ddb-269215df1a4e)  

Olen tehnyt tehtäviä vähän eri järjestyksissä niin näkyy screenshotteja :D  

Komennon avaus:  
sudo = superuser do eli tee toimi pääkäyttäjän oikeuksilla  
find = etsi-komento  
/etc/ = hakemisto, josta nyt etsitään   
-printf = print format; tulosta seuraavalla tavalla  
%T+ = muokkauspäivä ja aika  
%p = tiedoston nimi  
sort -r = sort reverse eli käänteisjärjestys    
head = 10 ensimmäistä riviä (oletus)  

(man-pages & [Geeksforgeeks](https://www.geeksforgeeks.org/sort-command-linuxunix-examples/))


## b) Gui2fs  
Muokkaa asetuksia jostain graafisen käyttöliittymän (GUI) ohjelmasta käyttäen ohjelman valikoita ja dialogeja. Etsi tämä asetus tiedostojärjestelmästä.  

Tässä osiossa menin ensiksi tekemään muutoksen kurssilla luodun Debian-virtuaalikoneen GUI:ssa ja yksinkertainen sellainen oli tiedoston luonti Documents-kansioon.  

![image](https://github.com/sibbee/p.hallinta/assets/149330317/ed4906b2-651a-4f13-93f7-cf400dbe4094)  

Tämän jälkeen siirryin takaisin terminaaliin ja suunnistin samaiseen kansioon nähdäkseni muutos. 
Komennolla ```$ find -printf "%T+ %p\n" | sort``` näkyi luomani tiedosto.   

![image](https://github.com/sibbee/p.hallinta/assets/149330317/6b740d44-ca26-40c8-b58f-834f4bccf6ec)  


## c) Komennus  
Tee Salt-tila, joka asentaa järjestelmään uuden komennon.  

Siirryin tätä varten ensin /usr/bin kansioon ja loin uuden tiedoston nimeltä "hello"  
Kirjoitin tiedoston sisään yksinkertaisen hello world -komennon  

![image](https://github.com/sibbee/p.hallinta/assets/149330317/9cfdc5c8-b69a-4d16-9aee-aa6dc63a6b75)  

Ajo-oikeudet asetin komennolla ```$ sudo chmod 755 hello```  ja seuraavaksi testasin toimiiko komento:  

![image](https://github.com/sibbee/p.hallinta/assets/149330317/04c9aa23-51b2-4d31-84cb-5dd590c7448f)  

Toimii. Tämän jälkeen siirryin /srv/salt polkuun ja loin tilatiedoston, 

![image](https://github.com/sibbee/p.hallinta/assets/149330317/de223a5d-66e3-48ba-b6c3-17f49c7834e1)  

Kopioin sen polkuun /srv/salt/cmd ja tarkistin että tiedosto löytyy  

![image](https://github.com/sibbee/p.hallinta/assets/149330317/fa9ea564-18c1-45cb-843f-430dc470b029)  

Löytyi, tämän jälkeen vielä itse tilan ajaminen. Succeeded = 1  

![image](https://github.com/sibbee/p.hallinta/assets/149330317/f50338f0-01cf-426a-a847-e99ef6242390)  


## d) Apassi  
Tee Salt-tila, joka asentaa Apachen näyttämään kotihakemistoja.  

Aloitin tehtävän katsomalla Tero Karvisen [ohjeita](https://terokarvinen.com/2018/04/03/apache-user-homepages-automatically-salt-package-file-service-example/) ja luomalla HTML-tiedoston.  

![image](https://github.com/sibbee/p.hallinta/assets/149330317/6bddba81-d93e-463a-8a74-c40b32f92de7)  

Tiedosto luotu, seuraavaksi loin tilatiedoston, jonka sisälle ohjeista saatu koodi  

![image](https://github.com/sibbee/p.hallinta/assets/149330317/279541f3-5231-43b3-a247-f4977d5feb78)  

Ja komennon ajo onnistuneesti. Kuva toisen ajokerran jälkeen sillä selkeämpi (idempotenssi; ei muutoksia)  

![image](https://github.com/sibbee/p.hallinta/assets/149330317/f2786dc7-9be5-4fce-b4dc-229c3650acd0)  




## e) Ämpärillinen  
Tee Salt-tila, joka asentaa järjestelmään kansiollisen komentoja.  

Samantyyppinen kun aikaisemmat tehtävät. Tätä varten loin aluksi uuden kansion "kansio", johon loin kolme snadia komentotiedostoa.  

![image](https://github.com/sibbee/p.hallinta/assets/149330317/50323d99-143b-4453-bf35-4fb504f09d0a)  

Sen jälkeen loin tilatiedoston, jonka sisälle seuraavasti:  
[Chris K.](https://github.com/bladexanarchy/pal_hal/blob/main/h5/h5.md)  auttoi  

![image](https://github.com/sibbee/p.hallinta/assets/149330317/63c04da7-b68c-48da-9571-3a6f87ba4f27)  

Ja vielä tilan ajaminen --local sillä tälle koneelle ei ole luotu minioneja  

![image](https://github.com/sibbee/p.hallinta/assets/149330317/e4028491-e593-49fc-8f8b-0881063ca9cd)  


## Lähteet  

Tero Karvinen 2018. Apache User Homepages Automatically - Salt Package-File-Service Example. Luettavissa: https://terokarvinen.com/2018/04/03/apache-user-homepages-automatically-salt-package-file-service-example/ Luettu: 26.11.2023  

Tero Karvinen 2023. Infra as Code 2023. Luettavissa: https://terokarvinen.com/2023/configuration-management-2023-autumn/  

Chris Kiuru 2023. h5 Luettavissa: https://github.com/bladexanarchy/pal_hal/blob/main/h5/h5.md Viitattu tehtävään e) 27.11.2023  

Geeksforgeeks.org. SORT command in Linux/Unix with examples. Luettavissa: https://www.geeksforgeeks.org/sort-command-linuxunix-examples/ Luettu: 26.11.





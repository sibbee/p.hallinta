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

Ensin /etc/ kansio:  

![image](https://github.com/sibbee/p.hallinta/assets/149330317/32646391-5ea7-41bf-9d3f-1b267d4a3bfb)  

Siellä näkyy tiedosto muokkaus.txt jonka loin ja testasin näkyykö  
Ja kotihakemisto:  

![image](https://github.com/sibbee/p.hallinta/assets/149330317/be6e6480-bfe3-4338-8ddb-269215df1a4e)  

Olen tehnyt tehtäviä vähän eri järjestyksissä niin näkyy screenshotteja :D  

Komennon avaus:  
sudo = toimin pääkäyttäjän oikeuksilla  
find = etsi-komento  
/etc/ = hakemisto, josta nyt etsitään   
-printf = print format; tulosta seuraavalla tavalla  
%T+ = muokkauspäivä ja aika  
%p = tiedoston nimi
sort -r = sort reverse eli uusimmat ensin  
head = 10 ensimmäistä riviä  


## b) Gui2fs  
Muokkaa asetuksia jostain graafisen käyttöliittymän (GUI) ohjelmasta käyttäen ohjelman valikoita ja dialogeja. Etsi tämä asetus tiedostojärjestelmästä.  

## c) Komennus  
Tee Salt-tila, joka asentaa järjestelmään uuden komennon.  

Siirryin tätä varten ensin /usr/bin kansioon ja loin uuden tiedoston nimeltä "hello"  
Kirjoitin tiedoston sisään yksinkertaisen hei maailma -komennon  

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



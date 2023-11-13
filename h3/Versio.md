# h3. Versio  

## a) Online  

Tässä tehtävässä tein uuden varaston [Tero Karvisen ohjeiden](https://terokarvinen.com/2023/create-a-web-page-using-github/) mukaisesti ja siten tämä kohta on valmis.  

![img](./ss.png)  

## b) Dolly  

Kopioin seuraavaksi vasta luodun varaston SSH-linkin  

![image](https://github.com/sibbee/p.hallinta/assets/149330317/218dd7d0-8514-488d-8e00-924ab998d24b)  
Uusi kansio myös tähän väliin  

![image](https://github.com/sibbee/p.hallinta/assets/149330317/a54d1fea-bcca-479e-aa1f-4825fb59138d)  
Seuraavaksi asensin Gitin  

![image](https://github.com/sibbee/p.hallinta/assets/149330317/56e1a37e-1a6b-4cab-8714-f2f5d57629db)  

Loin ssh-keygenilla avaimen ja luin "id_rsa.pub" (.pub -tiedosto on siis luotujen avainparin julkinen avain) ja kopioin tämän  

![image](https://github.com/sibbee/p.hallinta/assets/149330317/9b7c87bc-9ae1-478a-8e98-016bd4b59a4f)  

Kopioitu julkinen avain githubiin asetuksissa    

![image](https://github.com/sibbee/p.hallinta/assets/149330317/0d0be26b-d59a-485f-9907-27df6ea3f730)  

Tässä kloonataan aikaisemmin luodun varaston SSH-linkki h3-kansioon.  
Kloonaus näyttänee onnistuneen.  

![image](https://github.com/sibbee/p.hallinta/assets/149330317/876863c4-96d3-4f27-b796-837e29b5376f)  

![image](https://github.com/sibbee/p.hallinta/assets/149330317/fef6fe85-8b6a-4680-a776-39f43f547aa5)  
Loin tiedoston jossa on tekstiä  

![image](https://github.com/sibbee/p.hallinta/assets/149330317/91991324-c2d7-43b7-9c78-809b0a87a866)  
Oma käyttäjä  

![image](https://github.com/sibbee/p.hallinta/assets/149330317/4c25a83d-cde3-4e86-ab45-72e9f97c27af)  

```$ git add``` -komennolla lisätään tiedosto versionhallintaan ja tarkistetaan gitin status komennolla ```$ git status```  

![image](https://github.com/sibbee/p.hallinta/assets/149330317/ec13f71e-b626-4127-8316-2c6a8d16d53a)  
Tein ensimmäisen commitin komennolla ```$ git commit -m "eka commit"```  

![image](https://github.com/sibbee/p.hallinta/assets/149330317/c5ab638b-3fc8-4ea0-8592-452a388489f8)  

Sekä push, jonka jälkeen tiedosto ilmestyi varastooni  

![image](https://github.com/sibbee/p.hallinta/assets/149330317/e2d0bb0d-8a74-419b-bbf7-cb0a110d322a)  

Tarkistus selaimessa  

## c) Doh!  

Poistin gitin kautta testi.txt tiedoston  

![image](https://github.com/sibbee/p.hallinta/assets/149330317/463c82b5-4d78-4867-a4f6-0bd202483f86)  

Ja peruin tämän huonon muutoksen komennolla ```$ git reset --hard```  

![image](https://github.com/sibbee/p.hallinta/assets/149330317/789e3d6e-cdc2-4c20-8ff9-96560674c016)  
Kyseinen komento siis palauttaa tiedostot takaisin tilaan, joka on viimeksi commitattu.  

## d) Tukki

Apuna tässä tehtävässä Chris Kiuru  

![image](https://github.com/sibbee/p.hallinta/assets/149330317/bc91158e-2079-4b10-aef2-6098271c37fa)  

Nimi ja sposti näkyy. Lisäksi paikka ja aika sekä kommentti.  
Head = tämänhetkinen commit  
main = branchin oletusnimi  
origin = viittaa etä repoon  

(StackOverflow, https://stackoverflow.com/questions/75202925/meaning-of-head-main-vs-origin-head)  

## Lähteet  

Tero Karvinen 2023. Infra as Code 2023. Luettavissa: https://terokarvinen.com/2023/configuration-management-2023-autumn/  
StackOverflow 2023. Meaning of HEAD -> main vs origin/HEAD. Luettavissa: https://stackoverflow.com/questions/75202925/meaning-of-head-main-vs-origin-head  
Chris Kiuru 2023. h3. Luettavissa: https://github.com/bladexanarchy/pal_hal/blob/main/h3/h3.md  











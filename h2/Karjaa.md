# Karjaa  

# x) Lue ja tiivistä  

## What is the definition of "cattle not pets"?  

## Vagrant  
1. Päivitys ```$ sudo apt-get update```
2. Asennus ```$ sudo apt-get install vagrant virtualbox```
3. Alusta käyttöjärjestelmä ```$ vagrant init``` komennolla
4. ```$ vagrant up``` & ssh-yhteys ```$ vagrant ssh```
5. Kun haluat lopettaa käytön -> vagrant destroy
Ohjeet Tero Karvisen materiaalista https://terokarvinen.com/2017/04/11/vagrant-revisited-install-boot-new-virtual-machine-in-31-seconds/  

## Salt Vagrant  
1. Virtualisointiympäristö
   -> VirtualBox, Vagrant & tekstieditori
2. Vagrantfile tekstieditoriin määritystä varten
3. 

# a) Vagrantin asennus  
Asennusohjeet Tero Karvisen materiaalista https://terokarvinen.com/2023/salt-vagrant/   
Isäntäkäyttöjärjestelmäni Windows 10 

Latasin Vagrantin Windows AMD64 Versio 2.4.0 tästä linkistä: https://developer.hashicorp.com/vagrant/downloads   
Käyttöehtojen hyväsymisen jälkeen asennus alkaa   

![img](./h2.1.png)   

Tämän jälkeen ohjelma pyytää koneen uudelleenkäynnistystä.   
Sitä hyväksyessä tajusin, että ennen uudelleenkäynnistystä kannattaa tallentaa raportin muutokset   
Tajusin siis itse liian myöhään   
Vagrantin asentaminen onnistui.   

# b) Yksi maankiertäjä   
Tämän tehtävän ohjeet Tero Karvisen materiaalista https://terokarvinen.com/2017/04/11/vagrant-revisited-install-boot-new-virtual-machine-in-31-seconds/   

Ensiksi alustetaan käyttöjärjestelmä   

![img](./h2.2.png)   
Sama versio Ubuntusta tehtävänannon kanssa, vanha on mutta ei väliä

![img](./h2.3.png)   



![imh](./h2.4.png)   
Ssh-yhteyden muodostaminen onnistui. Kuvassa pari komentoa tilanteesta   

# c) Oma orjansa   

Tehtäväohjeet Tero Karvisen materiaaleista https://terokarvinen.com/2023/salt-vagrant/   

Ensimmäiseksi copypastesin ohjesivun valmiiksi kirjoitetun Vagrantfilen olemassa olevan tiedoston päälle   
Tämän jälkeen ```$ vagrant up``` ja odotetaan pieni hetki   

![img](./h2.5.png)   
(Todella pitkä lista masterin ja orjien määrityksistä)

![img](./h2.6.png)   

Tämän jälkeen ssh-yhteys masteriin, hyväksytään orjien avaimet ja testataan yhteys pingillä

![img](./h2.7.png)   

Herran ja orjien asennus on onnistunut.   

# Loput tehtävät verkossa   

## Idempotentteja komentoja   
Ensin 










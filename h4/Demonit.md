# h4 Demonit  
## x) Lue ja tiivistä  
- Infra as Code - Your wishes as a text file  
  Salt state / tilatiedoston ja sen kansion luominen;  
  - ```$ sudo mkdir -p /srv/salt/lol```, jossa -p luo hakemistot niiden puuttuessa  
  - ```$ sudoedit /srv/salt/lol/muuttuja.sls```  
  - Tiedostosisältöön ei tabeja!  
  - _File.managed_ lataa tiedostot salt masterista ja asettaa kohdejärjestelmään  
 
    https://www.geeksforgeeks.org/mkdir-command-in-linux-with-examples/  
    https://docs.saltproject.io/en/latest/ref/states/all/salt.states.file.html  
    https://terokarvinen.com/2023/salt-vagrant/#infra-as-code---your-wishes-as-a-text-file  

- top.sls - What Slave Runs What States  
  ddd  

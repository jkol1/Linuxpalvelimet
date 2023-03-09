# H13 Hello World tehtävä

## Python Hello World

Tein ohjelmille uuden kansion komennolla

    $ mkdir Hello

Tein ensiksi python Hello world ohjelman komennolla

    $ micro hellopython.py
    

![image](https://user-images.githubusercontent.com/112541753/224087752-d741af3a-8615-4e0c-aef2-4f4bb1a901c3.png)

Lopuksi kokeillaan, että se toimii ajamalla ohjelma komenolla

    $ python3 hellopython.py
    
![image](https://user-images.githubusercontent.com/112541753/224088703-f824ada0-356e-45a6-bd4e-a9eefc7d92a2.png)
Toimii.

## Bash Hello World

Aikaisempaan kansioon tehdään ohjelma komennolla

    $ micro hellobash.sh

![image](https://user-images.githubusercontent.com/112541753/224089322-e96cc05a-afe5-4edc-8dd3-acf9f0e80469.png)

Lopuksi kokeillaan ,että bash ohjelma toimii komennolla 

    $ bash hellobash.sh

![image](https://user-images.githubusercontent.com/112541753/224089645-20f1ff0e-5479-4488-927d-8920c6f4fbb8.png)

 
 ## Java Hello world
 
 Tehdään taas aikaisempaan kansioon ohjelma komennolla
 
    $ micro HelloJava.java
 
 ![image](https://user-images.githubusercontent.com/112541753/224090436-0992c0f4-0f8f-4bab-8cea-47c7a44edbd0.png)
 
 Kokeillaan, että ohjelma toimii komenolla
 
    $ javac Hellojava.java
    
![image](https://user-images.githubusercontent.com/112541753/224090772-e354b648-b759-436d-abd5-cb2254340635.png)

Java jäi asentamatta, joten asennetaan se nyt 

Ájetaan komennot

    $ sudo apt-get update
    $ sudo apt-get upgrade

Etsitään asennettava ympäristö komenolla 

    $ apt-cache search openjdk
    
Ja asennetaan openjdk-17-jdk versio

    $ sudo apt-get install openjdk-17-jdk

Kokeillaan, että asennus onnistui

    $ javac -version
 
 ![image](https://user-images.githubusercontent.com/112541753/224096449-6a9f7feb-0b26-415f-86f7-ac2e0b0f4e14.png)

Ja kokeillaan uudestaan tehtyä ohjelmaa

![image](https://user-images.githubusercontent.com/112541753/224100231-08dba3b1-65bc-475a-9792-3edcbbfa58ce.png)


## Lähteet

- https://terokarvinen.com/2023/linux-palvelimet-2023-alkukevat/#h13-hello-world
- https://terokarvinen.com/2018/hello-python3-bash-c-c-go-lua-ruby-java-programming-languages-on-ubuntu-18-04/
    

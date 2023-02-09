# Real Internet(tm) tehtävä

## Tiivistelmä https://terokarvinen.com/2017/first-steps-on-a-new-virtual-private-server-an-example-on-digitalocean/

- Muista hyvät salasanat
- palomuuri päälle ja muista tunnelin teko 
- Pakettien päivitys ja asennus muistettava
- Hyvät alkuaskeleet virtuaalipalvelimen vuokraukseen


## Virtuaalipalvelimen vuokraus

Valitsin linoden, jonka kautta vuokrasin virtuaalipalvelimen

Valitsin Debian 11 ja Saksan serverin
![image](https://user-images.githubusercontent.com/112541753/217784555-0226e5e9-51ce-4564-b973-1dfd26736fd4.png)

![image](https://user-images.githubusercontent.com/112541753/217784915-f4cd7655-18fb-4745-ac63-0527a90637a7.png)


## Alkutoimet

Otetaan yhteys palvelimeen ssh avulla
![image](https://user-images.githubusercontent.com/112541753/217785748-0343eb21-93e1-4474-a9fa-7d0f6df4d619.png)

Laitetaan palomuuri päälle

    $sudo apt-get install ufw
    $sudo ufw allow 22/tcp
    $sudo ufw enable
    
![image](https://user-images.githubusercontent.com/112541753/217786763-26db024e-5970-4da0-94f8-3d1d3b1328c7.png)

Luodaan uusi käyttäjä ja annetaan sille sudo oikeudet
    
    $sudo adduser jaakko
    $sudo adduser jaakko sudo
    $sudo adduser jaakko adm
    
 Kokeillaan toisella terminaalilla, että jaakko käyttäjällä pääsee palvelimeen kiinni
 ![image](https://user-images.githubusercontent.com/112541753/217788483-dbf3b638-be68-4fd4-a6c9-f41673ea297f.png)

Saatiin yhteys käyttäjällä jaakko, joten suljetaan root yhteys 

    $sudo usermod --lock root

Ja kielletään yhteyden teko jatkossa rootilla

    $sudoedit /etc/ssh/sshd_config 
 
![image](https://user-images.githubusercontent.com/112541753/217789304-27385da9-8d30-4dbd-8d9e-3b165ad646b9.png)

## weppipalvein ja testisivun korvaus

Asennetaan apache komenolla 
    
    $sudo apt-get install apache2
    
Avataan portti, jotta se näkyy muillekkin komenolla

    sudo ufw allow 80/tcp
    
Tarkistetaan selaimesta, että sivu on näkyvissä
![image](https://user-images.githubusercontent.com/112541753/217790295-f80103fd-956a-4001-970c-095ba4f7f1f7.png)

Korvataan testisivu omalla sivulla komenolla

    $echo Hello there | sudo tee /var/www/html/index.html
    
![image](https://user-images.githubusercontent.com/112541753/217792029-afcee641-4dd5-413d-b31e-c36608f66979.png)

Tarkistetaan vielä, että sivu on korvattu tekstillä Hello there

![image](https://user-images.githubusercontent.com/112541753/217792292-687089ff-e4fb-420a-813d-c9b250ff64b3.png)

Nyt on sivu vaihdettu.
    
## Merkkejä murtautumisista

Etsitään merkkejä murtautumisista komennoilla

    $sudo cat /var/log/auth.log
    $sudo cat /var/log/apache2/access.log

Ei vielä löytynyt merkkejä murtautumisista, mutta varmasti kun myöhemmin käy kokeilemassa löytyy murtautumisen merkkejä

15 Minuuttia myöhemmin kokeilin uudestaan, jos olisi tullut murtautumisia ja yksi yritys oli kerennyt odottelun välissä tulemaan.

![image](https://user-images.githubusercontent.com/112541753/217797955-a147eea2-71fe-4100-9dc2-e656c37f452e.png)


## Lähteet

- https://terokarvinen.com/2023/linux-palvelimet-2023-alkukevat/#h6-real-internettm
- https://terokarvinen.com/2017/first-steps-on-a-new-virtual-private-server-an-example-on-digitalocean/

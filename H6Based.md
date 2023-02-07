
# H6 Based Tehtävä

## Tiivistelmä

Getting started
- alottelijalle perusohjeita
- mistä löytyy conf ja muut tärkeät tiedostot, jotka configuroi serveriä
- serverin nimi  täytyy olla linkitetty ip osoitteeseen, jotta voi liittyä serveriin
- Nettisivun sisältö yleensä jaettu staattiseen ja dynaamiseen sisältöön

Name-based Virtual Host Support
- Jokaiselle Hostille tarvii erillisen ip osoitteen
- Nimipohjainen yleensä yksinkertaisempi vaihtoehto


## Etusivun vaihto apachelle

Aloiteaan tekemällä uusi kansio käyttäjälle, mihin tehdään uusi kotisivu

    $sudo mkdir public_sites
    
Tämän jälkeen mennään uuteen kansioon ja tehdään sinne index.html

    $cd public_sites
    $micro index.html
    
![image](https://user-images.githubusercontent.com/112541753/216764947-b9b434f7-4c5d-4e05-9819-f5b80a574495.png)

Tämän jälkeen mennään /etc/apache2/sites-available ja tehdään sinne uusi config

    $cd /etc/apache2/sites-available
    $sudoedit etusivu.conf
  
![image](https://user-images.githubusercontent.com/112541753/216765260-4571b6de-8561-436c-848d-6bfc8323d9bf.png)

Tämän jälkeen vaihdetaan etusivu komennoilla

    $sudo a2ensite etusivu.conf
    $sudo a2dissite 000-default.conf

Tämän jälkeen käynnistetään apache vielä uudelleen komennolla

    $sudo systemctl restart apache2
    
Käydään vielä tarkistamassa vaihtuiko uusi etusivu localhostiin, mikä aikaisemmin tehtiin
![image](https://user-images.githubusercontent.com/112541753/216765508-35692a38-60e1-41b6-ab9d-8b04e031ce5b.png)

Nyt on vaihdettu etusivu.

## virheilmoitusten vertailu

käydään tekemässä etusivu.conf tiedostoon virhe poistamalla nimen lopusta k

        $sudoedit etusivu.conf
![image](https://user-images.githubusercontent.com/112541753/217246717-908065ff-f1ee-4809-b75b-d78d94b568dc.png)

etsitään virheilmoitus komenolla

        $sudo cat /var/log/apache2/error.log
        
![image](https://user-images.githubusercontent.com/112541753/217246958-0ab6d4af-e605-4b55-8bab-ee0b707e6432.png)
Kertoo, että server configuration on kieltänyt yhteyden hakemistoon

tehdään configtest komennolla

        $sudo apache2ctl configtest

![image](https://user-images.githubusercontent.com/112541753/217247175-31cc2c69-c057-42d3-a2ca-42ee915ff719.png)

configtesti taas kertoo, että ei ole domain nimeä ja globaalisti pitäisi asettaa se, että ei tulisi enää viestiä

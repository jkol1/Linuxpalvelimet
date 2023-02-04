
# H6 Based Tehtävä

## 

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

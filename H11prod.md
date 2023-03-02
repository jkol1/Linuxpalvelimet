# H11 Prod tehtävä

## Djangon tuotantoasennus

Aloitetaan tekemällä jsite.conf 

![image](https://user-images.githubusercontent.com/112541753/222404480-b4dc3c4c-fe3d-4a78-ade2-b5b92c455e1e.png)


![image](https://user-images.githubusercontent.com/112541753/222404831-1e00e34b-ce63-4f63-9828-434f1ad5ce25.png)

Otetaan jsite.conf käyttöön komenoilla
    
    $ sudo a2ensite jsite.conf
    $ sudo a2dissite etusivu.conf

Tehdään config testi ennen apache2 uudelleen käynnistämmistä  
![image](https://user-images.githubusercontent.com/112541753/222405815-dab5bcb2-a5ce-4031-9aea-be4497c5ab2a.png)

    $ sudo systemctl restart apache2

käydään kokeilemassa curlilla, että vaihto onnistui    
![image](https://user-images.githubusercontent.com/112541753/222406471-3b87a8ad-f023-42a4-a739-ccc6ead72eb0.png)

Unohtui tehdä index.html joten tehdään se nyt:

    $ mkdir -p publicwsgi/jsite/static/
    $ echo "static test" | tee publicwsgi/jsite/static/index.html
    
![image](https://user-images.githubusercontent.com/112541753/222407266-efa3da3a-6e99-41a7-b3a5-ecd81bd88548.png)


Tehdään uusi kansio publicwsgi johon asennetaan virtualenv 

    $ cd publicwsgi/
    $ virtualenv -p python3 --system-site-packages env
    $ source env/bin/activate
    
Tehdään teksti tiedosto johon kirjoitetaan django

    $ micro requirements.txt

![image](https://user-images.githubusercontent.com/112541753/222408136-8fcbfb29-a5db-46ae-936f-385bc1bd6e33.png)

asenetaan pip:llä django lukemalla se tiedostosta välttääkseen kirjoitusvirheitä

    $ pip install -r requirements.txt

Tarkistetaan djangon versio

![image](https://user-images.githubusercontent.com/112541753/222409086-bf703315-41bf-4158-ba3f-648c88340d55.png)

Aloitetaan uusi django projekti komennolla
    
    $ django-admin startproject jsite
    
Kopioidaan config https://terokarvinen.com/2022/deploy-django/ ohjeista ja muutetaan polut oikeiksi

    $ sudoedit /etc/apache2/sites-available/jsite.conf

´![image](https://user-images.githubusercontent.com/112541753/222411799-f6f0ee8e-545e-4fd6-ad6a-e4664590fa33.png)

Asennetaan wsgi 

    $ sudo apt-get -y install libapache2-mod-wsgi-py3
    
    
Tehdään taas configtest ennen apachen uudelleen käynnistystä
![image](https://user-images.githubusercontent.com/112541753/222414138-9f1ab3d3-3a7d-48aa-ae21-cff173e4af05.png)

Käynnistetään apache2 uudestaan ja tehdään curlilla testi
![image](https://user-images.githubusercontent.com/112541753/222415020-19986ec2-4aba-41eb-8637-cc06b6298b7a.png)

Käydään muokkaamassa asetuksista debug pois päältä
![image](https://user-images.githubusercontent.com/112541753/222415510-0784d672-4e53-41c9-baf6-ddcb1564148a.png)

Käytetään touch komentoa ja käynnistetään apache2 uudelleen, että saadaan asetukset toimimaan

    $ touch jsite/wsgi.py
    $ sudo systemctl restart apache2
    
Nyt on Django asennettu tuotantoon, mutta käydään vielä lisäämässä pari asetusta settings.py, että saadaan tyylit takaisin ja ajetaan komento:    

    $ ./manage.py collectstatic

![image](https://user-images.githubusercontent.com/112541753/222417467-162a8f68-fee6-48d7-8abe-450a4cd1a5e6.png)

![image](https://user-images.githubusercontent.com/112541753/222417564-d3fd5fc2-d1f6-498b-97ce-7dbfb08f5b53.png)

![image](https://user-images.githubusercontent.com/112541753/222422054-4ae11182-37da-41ef-8323-4ffb73bb1bdc.png)

## Lähteet

- https://terokarvinen.com/2023/linux-palvelimet-2023-alkukevat/#h11-prod
- https://terokarvinen.com/2022/deploy-django/

    
    

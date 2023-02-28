
# H10 Django tehtävä

## Tietokantasovelluksen, jossa webbiliittymä tekeminen Djangon avulla

Aloitetaan tekemällä https://terokarvinen.com/2022/django-instant-crm-tutorial/ löytyvien ohjeiden mukaan.

Tein ensin uuden kansion komenolla 

    $ sudo mkdir Django

Ja sen jälkeen jatkoin asentamalla virtualenv

![image](https://user-images.githubusercontent.com/112541753/221495340-28fea4a5-9f34-43ce-82e3-42762e248512.png)

loin env kansion komenolla:

![image](https://user-images.githubusercontent.com/112541753/221495265-08639727-f0d0-410f-94ea-220d41e0049e.png)

    $ source env/bin/activate

Tehdään micro tiedosto, jossa on asennattavan ohjelman nimi. Tässä tapauksessa django
![image](https://user-images.githubusercontent.com/112541753/221505467-fcc929e9-43f0-4783-ac84-4aeba2773192.png)
![image](https://user-images.githubusercontent.com/112541753/221505553-6516b25c-bc3a-4214-96b7-b64d27711578.png)

asennetaan django komennolla: 

    $ pip install -r requirements.txt

Tarkistetaan, että django on nyt asennettu

![image](https://user-images.githubusercontent.com/112541753/221505936-a33e3505-8ad7-4c97-a3e3-667d663a1da4.png)

Tehdään uusi django projekti

![image](https://user-images.githubusercontent.com/112541753/221506543-89a05efd-1970-4a23-8719-4a0115cfc309.png)

Kokeillaan, että django toimii käynnistämällä se komennolla:
    
    $ ./manage.py runserver
    
![image](https://user-images.githubusercontent.com/112541753/221521632-5305d8ae-bb0d-4324-9ffe-da0ca2358524.png)

Toimii ja nyt voidaan alkaa tekemään tietokantaa sinne.

päivitetään tietokannat komennoilla:

    $ ./manage.py makemigrations
    $ ./manage.py migrate

Lisätään käyttäjä komenolla 
    
    $ ./manage.py createsuperuser
    
![image](https://user-images.githubusercontent.com/112541753/221522949-61068a88-f267-43ff-bf0b-61d2304a5f3d.png)

Kokeillaan, että uusi käyttäjä toimii 
![image](https://user-images.githubusercontent.com/112541753/221523521-9731b2d4-60e0-4eaa-be9b-5ba34f09bdd1.png)

Käyttäjä toimii, joten aletaan tekemään uutta tietojärjestelmää
Tehdään uusi tietokanta djangoon komenolla: 

    $ ./manage.py startapp "nimi"
    
Tämän jälkeen lisätään uusi tietokanta settings.py tiedostoon, jotta saadaan se näkyviin

    $ micro jaakontesti/settings.py
    
![image](https://user-images.githubusercontent.com/112541753/221525731-3c48f3a1-a6a4-499d-8cb8-01330fcbb58c.png)

Lisätään modeleita komenolla:
    
    $ micro jdb/models.py

![image](https://user-images.githubusercontent.com/112541753/221857150-a939bcad-808c-47ed-9bf0-a43ada5bf9c2.png)

Päivitetään taas tietokanta komennoilla:

    $ ./manage.py makemigrations
    $ ./manage.py migrate

Sen jälkeen lisätään vielä äsken tehdyt modelit admin.py tiedostoon 

    $ micro jdb/admin.py

![image](https://user-images.githubusercontent.com/112541753/221528255-a752e384-4d6b-4cf1-a155-2c3660497555.png)

Käydään katsomassa, että uusi tietokanta on nyt näkyvissä djangon admin paneelissa

![image](https://user-images.githubusercontent.com/112541753/221529396-6f3c01b4-496c-4336-82bb-403cf9d708fb.png)

Lisätään muutama vaate 

![image](https://user-images.githubusercontent.com/112541753/221530248-8c3da0ac-9d59-483f-92da-b7b007177332.png)
![image](https://user-images.githubusercontent.com/112541753/221530471-f323daa5-0c5e-4a36-9884-1b3c60d9f7f9.png)
![image](https://user-images.githubusercontent.com/112541753/221530833-2813e2f3-a23d-4e93-adda-255513cc10b2.png)


Vielä lopuksi vaihdetaan django näyttämään pelkkä vaatteen nimi muokkaamalla models.py tiedostoa

    $ micro jdb/models.py

![image](https://user-images.githubusercontent.com/112541753/221531539-8ed12c05-b9a8-415a-a440-b941bbb2602b.png)
![image](https://user-images.githubusercontent.com/112541753/221531859-e55b8f0a-b511-45ab-a3f8-899e26d6a224.png)

Nyt näkyy pelkkä vaatteiden nimi, eikä miten aikasemmin näkyi.

Vielä lopuksi tehdään uusi käyttäjä, joka voi muokata tehtyä tietokantaa.

![image](https://user-images.githubusercontent.com/112541753/221532633-755c2ce7-4e5f-482b-b1ae-f93bab2cf7d7.png)
![image](https://user-images.githubusercontent.com/112541753/221532880-ae9a2b82-4f08-40a0-a557-4f3018082463.png)

Testi käyttäjän lisäys onnistui ja kokeilin vielä, että sillä voidaan muokata tietokantaa lisäämällä vaate

![image](https://user-images.githubusercontent.com/112541753/221533872-d70892f3-32ff-4adf-b2d8-2934818134d1.png)

Vaatteen lisäys onnistui. Nyt on tehtynä tietokantasovellus, jossa weppiliittymä ja sitä pystyy kirjautuneet käyttäjät muokata.

## Lähteet

- https://terokarvinen.com/2023/linux-palvelimet-2023-alkukevat/#h10-dj-ango
- https://terokarvinen.com/2022/django-instant-crm-tutorial/


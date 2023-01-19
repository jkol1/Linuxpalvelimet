# Linuxin asennus virtuaali koneeseen


## Kone mihin asennetaan
Lenovo Thinkpad X1 Yoga 2nd signature edition

Processori = Intel i7 2.7GHz

Ram 16gb

käyttöjärjestelmä Windows 10 Pro

## Asennuksen aloitus
-10:30 Virtual boxin lataus Virtualbox.org kotisivun kautta ja asennus

-10:35 Debian imagen haku Debian.org sivustolta ja lataus. Latauksessa kesti hetki sillä tiedosto yli 3GB. 

-10:50 Debian image ladattu

-10:50 Virtual boxiin clickaamalla ratasta, jonka alla lukee new aletaan tekemään virtuaali konetta

otetaan expert mode nappia painamalla kaikki asetukset näkyviin
![vm4](https://user-images.githubusercontent.com/112541753/213422360-59f31a04-44f5-4ed8-8a36-7b7117cdfcdd.JPG)


Nimetään uusi virtuaali kone ja ISO imageksi valitaan aikaisemmin ladattu Debian image
![VM1](https://user-images.githubusercontent.com/112541753/213416845-0092e788-b475-43ae-8350-9b85cb280b4a.JPG)


valitaan haluttu ram muistin ja kovalevy muistin määrä. Valitsin 4000MB ja 60GB
![VM2](https://user-images.githubusercontent.com/112541753/213422151-465bc8b7-e547-4a67-941e-d0372a590076.JPG)
![VM3](https://user-images.githubusercontent.com/112541753/213422257-42802c24-1bc8-4cf2-8479-1044edb65f82.JPG)


painetaan Finish nappia ja tehdään virtuaali kone

-11:15 Mennään tehdyn virtuaalikoneen asetuksiin ja etsitään storagesta Controller IDe johon vaihdetaan pienen levyn kuvasta ladattu Debian image
![vm5](https://user-images.githubusercontent.com/112541753/213422478-7ae928a7-7058-40c3-a381-0386f09210d0.JPG)


-11:20 Tämän jälkeen käynnistetään virtuaalikone, ja valitaan ensimmäinen vaihtoehto

-11:30 Kokeillaan Internettiä ja valitaan iltasanomat
![is](https://user-images.githubusercontent.com/112541753/213416290-69eabf82-3b7d-4f74-8022-0483f57b70a5.JPG)


aloitetaan asennus ja valitaan oikeat asetukset

-11:45 avataan terminaali

![image](https://user-images.githubusercontent.com/112541753/213418320-d76de074-755d-4073-80e3-fa063f8aedbe.png)

ajetaan komento 

    $ sudo apt-get update
![image](https://user-images.githubusercontent.com/112541753/213421157-10f95843-550b-4688-8e45-253ac43ddc12.png)

jonka jälkeen päivitetään  komennolla

     $ sudo apt-get -y dist-upgrade
   
   
- 12:00 
 Lisätään palomuuri komennolla ja laitetaan se päälle
 
       $ sudo apt-get -y install ufw
       $ sudo ufw enable

Tämän jälkeen käynnistetään virtuaalikone uusiksi applikaatio menusta vasemmasta ylänurkasta

-12:15 Nyt on asennettu toimiva Linux virtuaalikoneeseen.









# Komentaja Pingviini tehtävä

## Micron asennus

--11:00 asennetaan micro komennolla

    $sudo apt-get install micro
    
![microasennus](https://user-images.githubusercontent.com/112541753/213995097-d1997412-e443-4f7a-8154-d0c8b36a5eb9.JPG)

Kokeillaan microa komennolla:

    $micro kokeilu
    
![microkokeilu](https://user-images.githubusercontent.com/112541753/214001666-67bc3bc2-34c9-413b-b4b1-115297f1f9c4.JPG)



## Raudan tarkistus

Suoritetaan komento:

    $sudo lshw -short -sanitize
    
![rauta](https://user-images.githubusercontent.com/112541753/213995450-2251272d-7d31-4f14-bff6-93bf3629a5e0.JPG)


Tiedoissa näkyy esimerkiksi virtuaalikonetta asennettaessa asetettu 4 GB muisti. Näkyy oikean koneen prosessori.

## Komentoriviohjelmien asennus

Asenetaan halutut ohjelmat komennolla

    $sudo apt-get install ohjelman-nimi
    
voidaan asentaa monta ohjelmaa samalla komennolla lisäämällä välilyönnin jälkeen haluttu ohjelma

Asensin ohjelmat sl, python3 ja cowsay

sl ohjelma tuo esiin kuvan junasta, joka "animoidusti" liikkuu, eikå tee muuta.

![testisl](https://user-images.githubusercontent.com/112541753/214008620-5aaca2ff-146d-482a-b2db-a0abda47fb27.JPG)


Python3 testi, että se toimii
![pythontesti](https://user-images.githubusercontent.com/112541753/214008670-9049650d-7b8c-4155-994c-a21cbe16461d.JPG)


cowsay tulostaa lehmän, joka sanoo sille kerrotun sanoman
![testicow](https://user-images.githubusercontent.com/112541753/214011192-37318f9e-e114-4d1b-81ea-de08c736d1c0.JPG)



## Tärkeiden tiedostojen esittely

/home/jaakkok tärkeä kotihakemisto

    $cd /home/jaakkok
    $ls -a
 ![home](https://user-images.githubusercontent.com/112541753/214012929-0c01c940-98e0-4426-93fd-85c6e7f21c03.JPG)


/var/log/syslog

    $cd /var/log
    $ls
    
![syslogi](https://user-images.githubusercontent.com/112541753/214014054-00073cb8-5e4c-4ca8-9b6a-7708161d3199.JPG)

    
 /etc/ järjestelmäasetukset
 
    $cd /etc/
    $ls
![järasetus](https://user-images.githubusercontent.com/112541753/214014782-13d9db4b-f0c6-41bd-88be-1bfcdce5b210.JPG)

cd
## Esimerkkejä grep-komennon käytöstä

Tehdään testi tiedosto

    $nano testi
![grep komento](https://user-images.githubusercontent.com/112541753/214016760-29ec7dd4-e3c6-4ff8-97dd-29103b70fcda.JPG)

grep komennolla etsitään montako kertaa "kokeillaan" löytyy testi tiedostosta.

    $grep -c 'kokeillaan' testi
    
![kokeillaan](https://user-images.githubusercontent.com/112541753/214017206-06b6be26-5196-4530-a92c-17798aeb80a2.JPG)
"kokeillaan" löytyy kerran tiedostosta.

Väritetään grep komennolla haetut avainsanat.

    $grep --color grep testi
    
![värikokeilu](https://user-images.githubusercontent.com/112541753/214018381-d84d0fd6-a773-45fd-8de4-5025ea8ab42c.JPG)
Tässä tapauksessa "grep" värjäytyi punaiseksi.


- 12:30  Tehtävät saatu valmiiksi ja raportointi loppuu.




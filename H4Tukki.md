# H4 Tukki tehtävä

## Tiivistelmä artikkelista https://earthly.dev/blog/command-line-tools/

-Artikkeli listaa 6 eri ohjelmaa, jotka ovat hyödyllisiä tuottoisille ohjelmoijille. broot, Funky, FZF, McFly, Better CD ja GitUpdate

-Selostetaan näiden ohjelmien hyötyjä työskentelyssä ja antaa esimerrkkejä niiden käytöstä.

-Kommenteissa myös paljon ehdotuksia eri ohjelmiin, joista voisi olla hyötyä työskentelyyn ja kerrotaan omia kokemuksia niiden kanssa.

## Lokien analysointi
Ajetaan komento:

    $sudo cat /var/log/syslog | less

![syslogianalyyis](https://user-images.githubusercontent.com/112541753/215389805-5e156d99-112c-4e79-9088-2ce2b4699246.JPG)
Esimerkki rivi syslogista. Kertoo, että kone on käynnistynyt onnistuneesti ja siihen kulunut aika


Ajetaan komento:

    $sudo cat /var/log/auth.log | less
 
![authlogianalyysi](https://user-images.githubusercontent.com/112541753/215389837-d3ecb2bc-7f5f-438e-a069-f26ac62b0da1.JPG)
Esimerkki rivi auth.logista. Kertoo komennon mitä käytetty, joka oli cat ja mihin tiedostoon se on käytetty, joka oli tässä syslog.
Kertoo myös käyttäjän, sekä ajan jolloin komento on suoritettu.

Ajetaan komento:

    $sudo cat /var/log/apache2/acces.log | less
    
![apachelogiesim](https://user-images.githubusercontent.com/112541753/215392929-54946727-b474-4324-a46e-d30dd3ef8fcd.JPG)
Esimerkki rivi apache2/acces.log:ista. Nähdään, että onnistuneesti otettu yhteys localhostiin ja selaimena mozilla firefox, sekä käyttöjärjestelmänä linux.

Ajetaan komento:

    $sudo cat /var/log/apache2/error.log | less
![errorlogi](https://user-images.githubusercontent.com/112541753/215393147-0528c9e1-80a9-4686-9789-3fdcbadbff9b.JPG)
Esimerkki rivi apache2/error.log:ista. On saanut SIGWINCH errorin ja sammuttaa apache2:en.


## Lokitapahtumia
Aiheutetaan auth.logiin tapahtuma käyttämällä komentoa:

    $sudo cat /var/log/auth.log
-Onnistuneesta lokitapahtumasta etsitään tieto komennolla:

    $sudo cat /var/log/auth.log | less
![image](https://user-images.githubusercontent.com/112541753/215387579-5198959d-7a38-496b-9171-7c9da80eefb2.png)

Kertoo komennon, mitä on käytetty COMMAND= jälkeen, kuka sitä käyttänyt sudo: jälkeen, tiedoston mihin käytetty komentoa ja ajan jolloin komentoa on käytetty.

-Virheelline loki apache2/acces.log:iin:
Avaataan firefox ja mennään localhostiin, mutta lisätään /testi perään
![errortesti](https://user-images.githubusercontent.com/112541753/215388921-b61da70f-e04e-4631-8e3c-6d53913fa5d6.JPG)

Etsitään virhelogi apache2/acces.log:ista komennolla

    $sudo cat /var/log/apache2/acces.log | less
    
![errornäyte](https://user-images.githubusercontent.com/112541753/215389520-e27a3de2-978b-43e3-9d3e-68326ec4ff61.JPG)



## Lähteet

- https://earthly.dev/blog/command-line-tools/
- https://news.ycombinator.com/item?id=27992073
- https://terokarvinen.com/2023/linux-palvelimet-2023-alkukevat/

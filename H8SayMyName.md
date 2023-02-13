# Say My Name Tehtävä

## Domainnimen vuokraus ja asettaminen osoittamaan virtuaalipalvelimeen

Valitsin namecheapin domainnimen vuokraamiseen ja rekisteröitymisen ja jaakkokolari.com domainnimen ostamisen jälkeen menin dashboardiin ja advanced dns asetuksiin lisätään A record, joka ohjaa nimen palvelimen ip-osoitteeseen
![image](https://user-images.githubusercontent.com/112541753/218428794-a9c37ab8-7b60-4949-8316-9841d988535f.png)

Pienen odottelun jälkeen jaakkokolari.com on nyt palvelimen sivun nimi
![image](https://user-images.githubusercontent.com/112541753/218433781-133caaab-99e2-44a6-aa2d-ee89d9e89b0d.png)

Tein vielä toisen A recordin ,että jaakkokolari.com sekä www.jaakkokolari.com molemmat ohjaavat palvelimen ip-osoitteeseen

Kokeilin eri selaimilla ja toimii.

![image](https://user-images.githubusercontent.com/112541753/218439432-4fefc7cc-163d-4ad6-ada6-16a350be6a6a.png)


## Host-komento 

![image](https://user-images.githubusercontent.com/112541753/218435546-821f198b-53d1-4557-b45a-4b6068df2cf3.png)
host komennon ajettua eka rivi kertoo, että jaakkokolari.com on nimenä ip osoittellee, joka on oma vuokrattu palvelin
Muista riveistä en saanut oikein muuta kuin ,että sähköpostia hoitaa alemmat osoitteet.

## Dig-komento

![image](https://user-images.githubusercontent.com/112541753/218436531-e0a73857-357e-4dbc-adab-ba276289f220.png)
Answer sectionissa kyselyn tulos, kertoo kysytyn osoitteen ip-osoitteen, sekä listätietoina : kauanko kului, palvelimen tietoja, milloin kyselty ja kyselyn koko.
Muista kohdista dig komentoa käytettäessä en oikein saanut selville mitä ne ovat.

## Lähteet
- https://terokarvinen.com/2023/linux-palvelimet-2023-alkukevat/#h8-say-my-name
- https://www.namecheap.com/support/knowledgebase/article.aspx/9837/46/how-to-connect-a-domain-to-a-server-or-hosting/

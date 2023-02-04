# H5 Hello web tehtävä


## Apachen esimerkkisivun vaihto

--10:55
Suoritetaan komento

    $echo Moikka | sudo tee /var/www/html/index.html

Tarkistetaan, että localhostin etusivu on vaihtunut apachen esimerkkisivusta
![image](https://user-images.githubusercontent.com/112541753/216277440-bb5128fc-0d71-4b7a-9aba-5adb31ee68a7.png)

## Käyttäjän kotisivu 

Tehdään uusi kansio nimeltä public_html, johon voidaan tehdä käyttäjän kotisivu

    $mkdir public_html
![image](https://user-images.githubusercontent.com/112541753/216278451-a0c47a72-eac1-43fe-8ba0-717fe8ca10b0.png)
 
Tämän jälkeen mennään public_html kansioon ja tehdään siellä index.html microlla

    $cd public_html/
    $micro index.html

Kirjoitetaan jotakin testiksi, että kotisivu toimii    
![image](https://user-images.githubusercontent.com/112541753/216279315-88c1704b-fad6-41c4-a9cb-185f8af82be4.png)
Jonka jälkeen tarkistetaan selaimella, että kotisivu näkyy
![image](https://user-images.githubusercontent.com/112541753/216279665-044521bd-7321-4eb5-b747-829b2724463a.png)

 
## Uusi käyttäjä
  
  Tehdään uusi käyttäjä komennolla:
  
      $sudo adduser testi
     
![image](https://user-images.githubusercontent.com/112541753/216280787-ecc46d45-feff-41e0-a03d-497cb8fbc412.png)
Tämän jälkeen vaihdetaan käyttäjää ja tehdään kotisivu testi käyttäjälle
Tehdään samat komennot kuin aikaisemmin

    $mkdir public_html
    $cd public_html
    $micro index.html
      
![image](https://user-images.githubusercontent.com/112541753/216282388-37108df3-3194-4937-beba-29702c59d9f0.png)
Ja tarkistetaan selaimella, että testi käyttäjän kotisivu toimii
![image](https://user-images.githubusercontent.com/112541753/216282755-68a8ff5c-800b-4ed3-ace3-344a388f86fa.png)

      
## Validi HTML5 sivu

Mennään muokkaamaan aikaisemmin tehtyä index.html

    $micro index.html
    
Mallipohjan kävin hakemassa Teron laittamasta linkistä läksyvinkeistä ja tein Validin HTML5 sivun
![image](https://user-images.githubusercontent.com/112541753/216284324-42649ae2-a7c4-483f-afa7-32c82ffff27f.png)
![image](https://user-images.githubusercontent.com/112541753/216288090-477e480a-b982-4753-aa99-5a53e3827759.png)

Tämän jälkeen tarkistetaan, että sivu on validi HTML5 sivu validaattorin avulla
![image](https://user-images.githubusercontent.com/112541753/216285923-11b4cfaf-2904-4919-b880-9030155b320b.png)
Tuloksena pari varoitusta, mutta muuten on validi HTML5 sivu nyt tehty.
![image](https://user-images.githubusercontent.com/112541753/216286544-97f5239e-c6a4-476c-859c-df2a8ff2470b.png)

## Indiehackers podcast 

Kuuntelin jakson: #191 Making a Living From the Paid Newsletter Ecosystem with Yaroslaw Bagriy of Newsletter Crew

- Puhuvat eri uutislehtiä varten olevista vaihtoehdoista. esim. wordpess, substack, ghost
- Mahdollisuudet rahantekoon nykyisen ekosysteemin avulla
- Vieras kertoo miksi ja miten aloitti newsletter crew:in
- Mitä uusia/vanhoja uutislehtien tekijöitä kannattaa pitää silmällä esim. the browser


## Lähteet 

- https://terokarvinen.com/2023/linux-palvelimet-2023-alkukevat/#h5-hello-web
- https://terokarvinen.com/2012/short-html5-page/
- https://www.indiehackers.com/podcast/191-yaroslaw-bagriy-of-newsletter-crew


   

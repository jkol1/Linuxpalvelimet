# H9 Sequel tehtävä

## Yrityssoftaa



## PostgreSQL asennus

Asennetaan postgreSQL komennolla

    $sudo apt-get -y install postgresql

Muistetaan käynnistää postgreSQL komenolla
    
    $sudo systemctl start postrgresql
   
Tehdään uusi tietokanta ja käyttäjä komennoilla

    $ sudo -u postgres createdb jaakko
    $ sudo -u postgres createuser jaakko

Tämän jälkeen kokeillaan, että kaikki toimii aloittamalla postgres komenolla 

    $psql
    
![image](https://user-images.githubusercontent.com/112541753/219300821-7405ea99-63aa-4d71-8efd-f669fe728ba7.png)

Nyt on PostgreSQL asennettu.
    
## CRUD

### Create
Tehdään testiksi sama taulu, joka löytyy https://terokarvinen.com/2016/03/05/postgresql-install-and-one-table-database-sql-crud-tutorial-for-ubuntu/

![image](https://user-images.githubusercontent.com/112541753/219302144-708f1cdb-c252-4f61-8c0c-395faaf1f10a.png)
Taulu tehty, mutta siellä ei vielä ole mitään tietoja joten lisätään muutama opiskelija opiskelija-tauluun

![image](https://user-images.githubusercontent.com/112541753/219303371-00b59d17-273e-4ea6-8466-0c00dfa539ff.png)
![image](https://user-images.githubusercontent.com/112541753/219303752-142631af-2cd7-4a2c-9c72-f24a5bb24d91.png)

### Read

Luetaan tietoa taulusta select komennolla.

![image](https://user-images.githubusercontent.com/112541753/219305277-dc79259c-b9f1-4cf4-afdc-abea450c4ab0.png)


### Update

Päivitetään Ville nimi ja lisätään sukunimi Vallaton

![image](https://user-images.githubusercontent.com/112541753/219304102-9bea76cc-8161-4acc-8e5f-4fb90c0bc164.png)

### Delete

Poistetaan tauluun tehty Tiina.

![image](https://user-images.githubusercontent.com/112541753/219304566-475c95d1-61bb-4601-8c2b-2daafa47b98d.png)


## Lähteet

- https://terokarvinen.com/2023/linux-palvelimet-2023-alkukevat/#h9-sequel
- https://terokarvinen.com/2016/03/03/install-postgresql-on-ubuntu-new-user-and-database-in-3-commands/
- https://terokarvinen.com/2016/03/05/postgresql-install-and-one-table-database-sql-crud-tutorial-for-ubuntu/


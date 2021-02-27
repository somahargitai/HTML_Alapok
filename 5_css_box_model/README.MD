# Box Model

A dobozmodell lényege, hogy a HTML elemei mind dobozokként jelennek meg, amelyeknek lehet egy kerete (border), egy külső eltartása, azaz margója (margin), illetve egy belső eltartása, ami a doboz szélétől választja el a tartalmat (padding).

Figyeljük meg a kódot és a böngészőben a megjelenést:

````css
      body {
        border: 0px;
        margin: 0px;
        padding: 0px;
      }
      div {
        border: 10px solid red;
        padding: 40px;
        margin: 10px;
      }
      ```

Külön megadtam a body stílusát. Erre azért van szükség, mert a böngésző alapértelmezetten rátesz a body-ra egy margót, az én böngészőmben éppen 8px szélességben. Ezt nem tűrhetem, úgyhogy minden ilyen stílust nullázunk.

Most, hogy ezt megoldottuk, észrevehetjük, hogy a két div között ugyanakkora az eltartás (margin), mint a böngészőablak széleihez. Pedig mind a kettőn van 10px margó. Ennek az az oka, hogy a margót a böngésző okosan számolja: tudja, hogy ezzel a minimális távolságot akarjuk biztosítani a szomszédos elemtől, tehát ha két elem margója találkozuk, akkor nem adja össze őket, hanem mindig a nagyobbikat veszi és azt alkalmazza.

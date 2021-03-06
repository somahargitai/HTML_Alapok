# Box Model

A dobozmodell lényege, hogy a HTML elemei mind dobozokként jelennek meg, amelyeknek lehet egy kerete (border), egy külső eltartása, azaz margója (margin), illetve egy belső eltartása, ami a doboz szélétől választja el a tartalmat (padding).

Figyeljük meg a kódot és a böngészőben a megjelenést:

```css
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

Most, hogy ezt megoldottuk, észrevehetjük, hogy a két div között ugyanakkora az eltartás (margin), mint a böngészőablak széleihez képest. Pedig mind a kettő diven van 10px margó, az együtt 20px. Ennek az az oka, hogy a margót a böngésző okosan számolja: tudja, hogy ezzel a minimális távolságot akarjuk biztosítani a szomszédos elemtől, tehát ha két elem margója találkozuk, akkor nem adja össze őket, hanem mindig a nagyobbikat veszi és azt alkalmazza.

## Oldalanként különböző eltartások, keretstílusok

Sok esetben egyáltalán nem akarjuk, hogy a border, a padding vagy a margin ugyanakkora legyen az elem mindegyik oldalán. Ilyenkor külön kulcsszavakkal be tudjuk állítani ezeket, egyenként:

```css
div {
 border-left: 10px;

 padding-right: 25px;
 padding-bottom: 1px;
 padding-left: 1px ;
 padding-top: 20px;

 margin: 8px;
}
```

A négy oldalt egy sorba is tömöríthetjük, a bordert a fenti helyett az alábbi módon is megadhatjuk. A sorrend: top, right, bottom, left

```css
div {
  padding: 20px 25px 1px 1px;
}
```

Gyakori, hogy a felső-alsó és a jobb-bal értékek megegyeznek. Ilyenkor elegendő két számot megadni, az első a top és a bottom értéke lesz, a másik a right és a left értéke

```css
div {
  padding: 2px 50px;
}
```

A bordernek stílust is meg lehet adni, pl. a _dotted_ esetében pöttyökből fog állni a keret. Ez manapság már kevésbé jellemző, ennél elegánsabb kiemelési módok is vannak, ezért egyelőre a sima keretet fogjuk alkalmazni, aminek a neve _solid_. Ezt a színnel együtt szintén egy sorban leírhatjuk, ahogy a kezdőpéldánkban és a mellékelt HTML-fájlban is láthatjuk:

```css
div {
  border: 1px solid red;
}
```

Fontos, gyakori használata a margónak, hogy középre igazítunk vele egy elemet. Erre az `auto` kulcsszó használatos, tehát ha vízszintese középre igazítjuk a body tartalmát, függőleges margót pedig nem akarunk neki adni, akkor a CSS kód így fog kinézni:

```css
div {
  margin: 0 auto;
}
```

Az ötös példafájlban ezeket még nem mutatom be, de nyugodtan módosítsátok a kódot, vagy ugorjatok előre a nyolcashoz, ott lesz ezekre példa.

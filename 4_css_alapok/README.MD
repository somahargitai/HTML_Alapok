# CSS alapok

A stílust leíró kódot beírhatjuk a HTML fájl `<head>` részébe is, a HTML tagek belsejébe is, és külön fájlba is, `<link>` taggel hívatkozva. Én it most az előbbit fogom alkalmazni, de ugyanilyen jó megoldás a külön CSS fájl is. A HTML kódba nem szokás már stílusparancsokat beírni, szerencsésebb szétválasztani a HTML és a CSS kódrészt.

Helyezzünk el `<style>` taget a `<head>`-ben, majd megírhatjuk az első stílusparancsunkat:

```css
p {
  color: red;
  font-size: 18px;
  font-weight: bold;
}
```

Minden stílusleírás először azzal az elemmel kezdődik, amit szeretnénk módosítani - jelen esetben ez egy bekezdés. Ezután **kapcsos zárójelben** kell megírnunk a stílusparancsokat. A VS Code segít abban, hogy mik az elérhető lehetőségek, de megleshetjük őket a w3schools vagy az MDN oldalán is, pl. a szövegszínekről itt olvashatunk: https://www.w3schools.com/cssref/pr_text_color.asp

Minden parancs után **pontosvessző** következik.

A HTML-fájlt a böngészőben megnyitva láthatjuk, hogy csak a szöveg egy része kapta meg a stílusokat. Ez azért van, mert csak az a szövegrész lett betéve `<p>` tagbe, a többi csak egy `<div>`-ben van benne.

Hozzáadtam a következő stílusparancsokat is:

```css
span {
  color: green;
}
```

Így a spanbe zárt szavak zöldek lettek. Ha ezt a három sort kitöröljük, a spanek tartalma is piros lesz. Ez azért van, mert minden elem __örökli__ az őt tartalmazó szülő elem stílusát.

Amikor hozzáadtam ezt a három sort, a span tartalmára egyaránt vonatkozott a bekezdés stílusa és a span stílusa is. A szín kérdésében a kettő ellentmondott egymásnak, de a span stílusa győzött, mert ez volt a specifikusabb stílus, szemben a piros szöveggel, ami csak örökölt stílus volt.
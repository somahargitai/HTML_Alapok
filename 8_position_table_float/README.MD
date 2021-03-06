# Position, Table, Float

A korábbi példákból kiderült, hogy alapértelmezetten minden HTML elem szépen, egymás után, "befolyatva" jelenik meg. Némelyik blokkszintű lesz (tehát kitölt egy teljes vízszintes sávot), némelyik sorközi elem (mint egy szöveg, kép, link), de a sorrendjük sosem változik.

Amikor egy menüt készítünk, hasábokat, egy oldalsávot, akkor ezen változtatni akarunk. Erre többféle megoldás is van, például berakhatunk minden elemet egy táblázatba és a rácsát 0 vastagságúra állíthatjuk. Ez a megoldás viszont számos sebből vérzik, sok problémát pedig nem is lehet így megoldani.

A _float_ property azt mondja meg, hogy az adott HTML elemünk után soron következő elemet ne a szokásos módon tegye be, hanem folyassa körbe.
Erre az alappélda egy kép, ami körül szeretnék körülfolyatni a szöveget.

A _position_ property alkalmas arra, hogy egy elemet teljesen kiszakítsunk a helyéről. Megadhatjuk, hogy a "normális helyéhez" (`position: static;`) képest hova kerüljön, de akár teljesen ki is vehetjük a normál szabályok alól és a böngészőablak tetejére tehetjük.

## Középre igazítás

Ahogy az ötös példában már láttuk, a középre igazítást a `margin: 0 auto` fogja nekünk megoldani. Tegyünk rá egy keretet is

```css
div#content {
  width: 500px;
  margin: 0 auto;
  padding: 5px;
  border-top: 20px solid red;
  border-right: 25px solid blue;
  border-bottom: 1px solid red;
  border-left: 1px solid black;
}
```

Ezzel azt mondjuk, hogy - megfelelően a dobozmodellnek - a div tartalmának a szélessége legyen 500 pixel, legyen középre igazítva, fölötte-alatta ne legyen margó, és mindez kapjon megfelelő színnel az adott oldalakon kereteket.

## Float

Először folyassuk körbe a kép körül a szöveget:

```css
img {
  float: left;
}
```

Láthatjuk, hogy a kép tényleg balra került, a sorban utánakövetkező szöveg pedig beúszott a kép mellé, majd a kép után teljes szélességben folytatódott.

## Position

### Fixed

Ez már izgalmasabb probléma. Kezdésnek helyezzünk el egy szöveget úgy, hogy a böngészőablak jobb felső sarkában legyen és az böngésző méretétől függetlenül mindig tartsa is meg a helyét. Erre szolgál a _position: fixed_. A szöveget betettem egy `<span>`-be és mivel csak ezt az egy spant szeretnénk elmozgatni, egy id-t is rá kell akasztanunk:

```html
<span id="i_am_griffo_fan"> Francesco Griffo 4EVA! </span>
```

Már pozicionálhatjuk is a szöveget:

```css
      #i_am_griffo_fan {
        position: fixed;
        top:5px;
        right: 50px;
```

A példafájlban tettem rá keretet, színeket és szövegstílust is, az esztétikai élményért nem vállalok felelősséget `:-)`

### Relative

Egy másik lehetőség, hogy egy elemet a _normál pozíciójához képest_ helyezünk el. Például ha egy szövegben beteszünk egy szót egy spanbe és ennek adunk relative positiont, akkor a mindenkori szövegfolyambeli helyéhez képest mozdul el. A szövegbeli helye meg is marad, oda nem folyik be másik szó, ő pedig gond nélkül ráúszik akár a szöveg többi részére.

A példafájlban megtaláljátok a szövegben ezt a spant, ismét egy id-val különböztettem meg, majd megadtam a stílust:

```css
#creepy_style {
  position: relative;
  left: -60px;
}
```

### Absolute

A `position: absolute;` nagyon hasonló a relative-hoz. Csakhogy: 
- Az elemet a `position: fixed;`-hez hasonlóan teljesen kiveszi a folyamból, nem hagyja meg a helyét, mint ahogy a `position: relative;` kapcsán láttuk.
- a pozicionálás alapjául nem a normális szövegfolyambeli helyet veszi. Ehelyett megnézi, hogy milyen HTML-elemekben van ő benne. Saját magától indul felfelé a hierarchiában és megkeresi az első elemet, aminek a positionje nem `position: static;` (ami az alapértelmezett), hanem ettől különböző. Ennek az elemnek a bal felső sarkát tekinti majd kiindulópontnak.

Ezt kicsit nehéz megemészteni, lássuk a példát. A példafájlban a szöveget tartalmazó nagy divben betettem a szöveg alá ezt a másik divet:

```html
      <div id='absolute_typo_nerd'>Typography 2021</div>
```

Pozicionáljunk!

```css
      #absolute_typo_nerd {
        position: absolute;
      }
```

Amíg csak ezt írtuk meg, egyetlen változást látunk: kikerült a szövegünk az őt tartalmazó div-ből. Mint megbeszéltük, a `position: absolute;` kirántja az elemet a normál folyamból: itt még "emlékszik", hogy hol kéne lennie, de nem tartja fent neki a helyet. Ezért a szokott helyén próbál lenni, miközben az őt tartalmazó div elem többé nem vesz róla tudomást.

Bővítsük a kódunkat:

```css
      #absolute_typo_nerd {
        position: absolute;
        top: 1px;
        left: 1px;
      }
```

Így már minden más. A divünk megkereste, hogy az őt tartalmazó elemek közül melyik a legközelebbi, aminek a positionje nem static. Ezt rögtön is megtalálta a közvetlen szülőelemében, a content id-val ellátott divben. Amikor megadtam a top és a left segítségével

```css
            #absolute_typo_nerd {
        position: absolute;
        top: 300px;
        left: -156px;
        padding: 10px;
        border-right: 5px solid black;
        border-left: 20px solid blue;
        background-color: beige;
      }
```
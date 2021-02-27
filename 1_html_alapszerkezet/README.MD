# A HTML alapszerkezete

A HTML-ben minden elem HTML-tagek közé van zárva. Minden HTML-tag egy nyitó- és egy záróelemből áll. A záróelemben egy perjel jelzi, hogy ez az adott elem vége. Például ha egy szöveget akarsz beilleszteni, akkor azt a paragraph tagbe fogod beírni:

```html
<p>
The quick brown fox jumps over the lazy dog
</p>
```

A fő html-tag `<html>`. Ebben kell elhelyezni a `<head>` és a `<body>` elemet. A body tartalmaz minden szöveget és más elemet, amit látni akarsz a weboldalon. A head írja le a többi szükséges háttérinformációt: mi legyen a weboldal címe (ami megjelenik a böngészőfülön), milyen stílusokat alkalmazzunk a body elemein, vagy éppen mi történjen, ha megnyomsz egy gombot (_ehhez majd Javascript kódra lesz szükség_).

```html
<html>
<head>
  <title>DOG !</title>
</head>
<body>
  The quick brown fox jumps over the lazy dog
</body>
</html>
```

További kiegészítő elemek fordulhatnak elő a head-ben, illetve a html tagen kívül is. Ezek egyelőre nekünk nem fontosak, de hasznos, ha tudunk róluk. Az alábbi kódot a HTML5 Boilerplate bővítmény gyártja le neked a VS Code-ban HTML kezdőkódként, ezért ezeket magyarázom meg itt, mint tipikus alapelemeket:
- DOCTYPE : Minden szabványos HTML fájl ezzel kezdődik. Ez mondja meg a böngészőnek, hogy "mire számítson". Főleg a HTML régi verziói miatt szükséges
- Internet Explorer megjegyzések : mivel még mindig használnak emberek régi verziós, borzasztó böngészőket, amik nem tudják a modern kódot jól használni, ezeknek "üzen" ez a pár sor.
- `meta` tagek: itt is a böngészőnek üzenünk, elsősorban a régi böngészőkre tekintettel. Rögzítjük, hogy Unicode karakterkódolást fogunk használni és nem egy régit, pl. a 191 betűformát ismerő _ISO/IEC 8859-2_ karakterkódolást, ami az UTF-t előtt használatos volt magyar honlapokon
- `link` tagek: ha másik fájlból szeretnénk stílusbeállításokat használni (azaz CSS-t), itt tudunk hívatkozni a fájlra.

```html
<!DOCTYPE html>
<!--[if lt IE 7]>      <html class="no-js lt-ie9 lt-ie8 lt-ie7"> <![endif]-->
<!--[if IE 7]>         <html class="no-js lt-ie9 lt-ie8"> <![endif]-->
<!--[if IE 8]>         <html class="no-js lt-ie9"> <![endif]-->
<!--[if gt IE 8]>      <html class="no-js"> <!--<![endif]-->
<html>
  <head>
    <meta charset="utf-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <title>Title of the website</title>
    <meta name="description" content="">
    <meta name="viewport" content="width=device-width, initial-scale=1">
    <link rel="stylesheet" href="./styles.css">
  </head>
  <body>
    The quick brown fox is lazy
  </body>
</html>
```

# class és id

Hasonlóan a print szövegszerkesztőkhöz, a böngészőben is szeretnék számos elemnek azonos stílust adni, vagy éppen sok hasonló elem közül kiemelni egyet és speciális stílusokat adni neki. Erre szolgálnak a classok és id-k.

## class

Jelöljük meg a div elemeket classokkal:

```html
<div class="egyik">Egyik div</div>
<span class="egyik">Ez egy span</span>
<div class="masik">Másik div</div>
```

Ezután már rájuk is akaszthatunk stílusokat. A classok nevei elé mindig teszünk egy pontot, ezzel jelöljük, hogy ezek nem standard HTML elemek, mint egy bekezdés, hanem classok:

````css
      .egyik {
        border: 10px solid red;
      }
      .masik {
        border: 5px dotted #123456;
      }
      ```
````

Akárhány elemet jelölünk meg, mindegyik megkapja ugyanazokat a stílusokat. Ezen a példán egy span és egy div is megkapta ugyanazt a stílust és minden további nélkül működött is.

## id

Az id teljesen megyezik a class-szal, a különbség mindössze annyi, hogy egy adott id-t csak egy elem használhat az egész HTML-ben, illetve hogy pont helyett kettőskereszttel írjuk le a stílusukat. Például:

```html
<div class="egyik" id="ezegyid">Egyik div</div>
```

```css
.egyik {
  border: 10px solid red;
}
#ezegyid {
  padding: 60px;
}
```

## több class egy elemen

Egyetlen HTML több classt is használhat egyszerre. Ilyenkor persze ügyelnünk kell rá, hogy mi történik, ha több class is leírja ugyanazt a tulajdonságot. Az alábbi példában három class lesz egy elemen. Ha ütközik két parancs, akkor az "erősebb" győz, például ha a div egyetlen classa mondja, hogy kék legyen a keret, a másik kettő pedig azt, hogy piros, akkor a piros fog győzni. Ha 1-1 az állás, akkor a sorrend számít

```html
<div class="egyik masik harmadik">Egy div</div>
```

```css
.egyik {
  border: 5px solid blue;
  padding: 10px;
}
.masik {
  border: 5px solid red;
  margin: 5px;
}
.harmadik {
  border: 5px solid red;
  background-color: lightblue;
}
```

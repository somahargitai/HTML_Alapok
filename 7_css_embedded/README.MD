# CSS parancsok egymásba ágyazva és egymást erősítve

CSS parancsokat megadhatunk egymással kombinálva is. Például ha minden olyan spant szeretnénk kék kerettel ellátni, amik egy divben vannak, akkor használhatjuk ezt a kódot:

```css
   div span {
        border: 5px solid blue;
      }
```

Fontos, hogy a div és a span között __szóköz__ van. Ezzel jelöljük, hogy egymásban lévő elemekről van szó. Sokszorosan is beágyazhatjuk őket, kombinálhatjuk classokkal is, például egy divben lévő .egyik classban lévő divben lévő divben lévő spanre hivatkozhatunk így: `div .egyik div div span {...`.

Teljesen más a helyzet, ha egy HTML elemhivatkozás és egy class- (vagy id-) hivatkozás között nincs szóköz: 

```css
      div.egyik {
        color: seagreen;
        border: 10px solid red;
      }
```

Ez esetben már nem a divben lévő .egyik classú elemről van szó, hanem egy olyan divről, ami egy .egyik classba tartozik. Mint amilyen ez az elem: `<div class="egyik">`

További jelölők állnak rendelkezésre arra, hogy milyen szintű a szülő-gyermek kapcsolat. A `div .kedves` minden divben lévő kedves classú elemre vonatkozni fog, ugyanakkor a `div > .kedves` már csak azokra a divben lévő kedvesekre, amelyek _közvetlenül_ a divben vannak. Tehát egy divben lévő spanben lévő .kedves elemre már nem.
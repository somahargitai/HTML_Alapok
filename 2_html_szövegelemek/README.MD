# Alapvető elemek

- `p` - bekezdés elem szövegek tárolására
- `h1`, `h2`, `h3` ... - címsorok. h1-ből csak egy lehet egy weboldalon. Elsősorban nem a stílus miatt különböztetjük meg őket, hanem mert a Google és más keresők a weboldal indexelésekor ezeket az elemeket nézik címként, így (is) gyűjtenek információt a weboldal tartalmáról. Az alapértelmezett stílusuk más, mint a paragrafusoké, de ez tetszés szerint módosítható, nincs jelentősége
- `a` - linkek a szövegben. A nyitó- és záróelem közé megy a megjelenítendő szöveg, a nyitóelem belsejében pedig a href attribútum fogja megadni az URLt: `<a href="http://google.com">Google</a>`
- `img` - képek. Hasonlóan a linkekhez, itt az `src` attribútum fogja megadni a kép helyét. Például az `<img src='./kep.jpg' />` a HTML fájllal azonos mappában fogja keresni a `kep.jpg` fájlt. Az `<img src='../../images/masikkep.jpg' />` kettővel feljebb fog menni a mappastruktúrában és az ott lévő `images` mappában keresi majd a `masikkep.jpg` nevű fájlt.
Láthatjuk, hogy ez a tag különleges: nincs záróeleme, ehelyett a nyitóelem végén van egy `/` jel. Ez egy úgynevezett "önlezáró" elem - egy kép esetében egyszerűen nem lenne értelme egy nyitó- és egy záróelem közötti szövegnek.
- `ul`, `li` - felsorolás. Létezik unordered list és ordered list változata is
- `table`, `td`, `tr`, `th` - táblázat, sorok, oszlopok, fejlécek
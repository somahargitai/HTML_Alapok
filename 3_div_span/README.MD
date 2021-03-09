# Div és Span

Ez két speciális elem. Semmilyen saját funkciójuk nincsen, csak az, hogy konténerként magukba foglaljanak másokat. Ennek különösen a stílusok bevezetésénél lesz majd jelentősége.

Korábban észrevehettük már, hogy a bekezdések `<p>` tagjei és a címsorok mindig kitöltötték a teljes sort, míg a linkek, képek és a tulajdonképpeni szöveg szépen megfért egy sorban. Az azért van, mert a bekezdés és a címsorok __blokk szintű elemek__, míg a képek, a linkek és a szöveg __szövegközi elemek__. Pontosan ezért van szükségünk külön `<div>` és `<span>` elemre. Előbbi blokk szintű elem, utóbbi szövegközi elem.

## Szemantikus elemek és SEO

A korábban vett elemek (link: `<a>`, bekezdés: `<p>` stb.), illetve a div és a span mellett van még egy fontos csoport: a szemantikus elemek. Ezek a divhez és a spanhez hasonlóan befoglaló elemek, de velük szemben nem általános célúak. A feladatuk az, hogy egy weboldal világosan elkülönülő, jellemző elemeihez használjuk őket. Például egy blog vagy híroldal esetében használhatjuk az `<article>` elemet. Ez különösen fontos SEO szempontból (Search Engine Optimization). Amikor egy keresőmotor, mint a Google (vagy a Bing, a DuckDuckGo, a Yandex, az Ecosia, a Baidu) indexeli a weboldaladat, megpróbálja értelmezni a tartalmat. Adatokat gyűjt az oldal tartalmáról, tulajdonosáról, céljáról, témájáról. A szemantikus elemek ebben nagyban segítik.

A legfontosabbak:
- `<section>` - bekezdésnek, tartalomnak, kapcsolati információknak való befoglaló elem
- `<footer>`
- `<header>`
- `<nav>` - navigációs menü az oldal főbb elemeinek
- `<main>` - az oldal fő tartalmi elemeinek

A teljes listáért ajánlom a [W3Schools vonatkozó cikkét](https://www.w3schools.com/html/html5_semantic_elements.asp)

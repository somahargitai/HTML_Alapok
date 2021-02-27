# Div és Span

Ez két speciális elem. Semmilyen saját funkciójuk nincsen, csak az, hogy konténerként magukba foglaljanak másokat. Ennek különösen a stílusok bevezetésénél lesz majd jelentősége.

Korábban észrevehettük már, hogy a bekezdések `<p>` tagjei és a címsorok mindig kitöltötték a teljes sort, míg a linkek, képek és a tulajdonképpeni szöveg szépen megfért egy sorban. Az azért van, mert a bekezdés és a címsorok __blokk szintű elemek__, míg a képek, a linkek és a szöveg __szövegközi elemek__. Pontosan ezért van szükségünk külön `<div>` és `<span>` elemre. Előbbi blokk szintű elem, utóbbi szövegközi elem.
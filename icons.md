# Icons

Er zijn een aantal manieren om icoontjes op je website te plaatsen, maar er is één manier die de beste is: met SVG. (tenminste dat denk ik)

## Wat zijn SVGs?
SVGs (Scalable Vector Graphics) zijn een soort net niet fotobestanden die berekeningen opslaan voor vormen. In plaats van pixels op bepaalde plekken, wordt opgeslagen waar bijvoorbeeld een lijn of een cirkel staat en welke vorm en kleur deze bijvoorbeeld heeft. Omdat dit gedaan wordt met berekeningen, kunnen ze een andere grootte krijgen zonder dat de kwaliteit vermindert.

## Hoe voeg ik een SVG toe?
In plaats van dat je een `img` element aanmaakt, plak je een `svg` element in je HTML. Je kunt dit element halen van een aantal websites, maar ik raad de volgende twee aan:

- [Material Icons](https://fonts.google.com/icons) is van Google. Dit zijn alle icons die zij gebruiken voor bijvoorbeeld Android en YouTube. Dit zijn simpele maar duidelijke icoontjes. Je downloadt hier een SVG bestand en moet de inhoud kopieren en in je HTML plakken. Icons hebben hier standaard een hoogte en breedte van 24px.
- [Heroicons](https://heroicons.com/) is van de makers van TailwindCSS. Deze icons hebben iets meer stijl, maar er zijn minder icons dan op Material Icons. Als je hier over een icon hovered, kan je op 'Copy SVG' drukken om de HTML te kopieren, zodat je deze gelijk in je bestand kunt plaatsen. Elementen krijgen hier standaard de classes `w-6` en `h-6` uit Tailwind. Deze staan voor een hoogte en breedte van 24px. Ik raad aan om deze classes zelf toe te voegen als je geen Tailwind gebruikt.

Beide websites hebben outlined en filled icons. Dit zijn varianten van icoontjes met vulling of zonder vulling. Vaak geven websites pagina's in een sidebar icoontjes, en geven ze de geselecteerde pagina een icoontje met vulling.

## Kleur aanpassen
Het fijnste aan SVGs is dat je heel makkelijk de kleur kunt aanpassen. Alle icons van Heroicons hebben dit standaard, maar bij die van Material Icons moet je het volgende toevoegen aan het `<path>` element (die in het `<svg>` element zit): `fill="currentcolor"`. Je kunt vervolgens heel simpel de kleur veranderen als volgt:

```css
.class-van-jouw-icon {
    color: red;
}
```

# Responsiveness

Met een goede layout kun je de meeste van je responsiveness doen, maar helaas niet alles. Soms wil je bepaalde elementen juist verstoppen of toevoegen op andere soorten schermen. Hier leg ik uit hoe dat kan.

Voordat we hiermee beginnen moet ik heel even kort twee dingen uitleggen: Het verschil tussen `display: none` en `visibility: hidden`, en `overflow`.

## Het verschil tussen `display: none` en `visibility: hidden` (en `opacity: 0`)
Als je `display: none` gebruikt, verdwijnt het element overal, behalve je HTML. Het element zal niet zichtbaar zijn op de pagina, en heeft geen invloed op de positie van andere elementen. Je kunt het wel nog steeds ophalen met `document.querySelector()` of iets soortgelijks. De gebruiker kan er ook niet meer op klikken (maar kan wel handmatig `display: none` uitzetten, dus gebruik dit niet als bescherming voor iets).

Als je `visibility: hidden` gebruikt, zal het element onzichtbaar worden, maar zal het zijn plek wel behouden, en zullen het nog steeds invloed hebben op de positie van andere elementen. Je kunt ook niet klikken op een element met `visibility: hidden`.

Als je `opacity: 0` gebruikt, zal het element onzichtbaar worden en zijn plek behouden zoals bij `visibility: hidden`. Je kunt alleen WEL op het element klikken.

## Overflow (https://developer.mozilla.org/en-US/docs/Web/CSS/overflow)
Standaard staat `overflow: visible` aan. Dit betekent dat als de inhoud van een element te groot is voor dat element zelf, de inhoud buiten het element zichtbaar zal zijn. Als je element door de inhoud breder is dan het scherm, ga je opzij kunnen scrollen, wat je niet wilt (opzij scrollen is zelden een goed ding als het op een groot deel van de pagina gebeurt).

Als je `overflow: hidden` aanzet, zal alle inhoud die buiten het element komt verdwijnen en zul je niet opzij kunnen scrollen in het voorbeeld van net.

Als je `overflow: auto` aanzet, zal er een scrollbar verschijnen wanneer het element te groot wordt. Je kunt ook `overflow-y: auto` gebruiken om alleen verticaal een scrollbar te laten zien, of `overflow-x: auto` voor een horizontale scrollbar.

Ik raad aan om even het voorbeeld uit deze link te bekijken: https://developer.mozilla.org/en-US/docs/Web/CSS/overflow

## Media-queries
Nu kunnen we echt beginnen met responsiveness. Het is altijd belangrijk om eerst te bedenken wat er uberhaupt moet gebeuren als je het scherm kleiner wordt. Je kunt dit gewoon in je hoofd doen, maar het kan geen kwaad om dit te documenteren door extra designs te maken op bijvoorbeeld Figma. Als je dit weet, kan je bepalen welke wijzigingen je wilt maken in CSS op bepaalde resoluties. Dit kan met behulp van `media`-queries:

```css
@media only screen and (max-width: 480px) {
  body {
    background-color: lightblue;
  }
}
```

In dit voorbeeld wordt de achtergrond kleur lichtblauw, zolang het scherm niet breder is dan 480px. Op de meeste mobiele apparaten is de achtergrond dus lichtblauw, terwijl deze op tablets en computers gewoon wit zal zijn. Je kunt dit gebruiken om bijvoorbeeld een navbar te verstoppen op mobiele apparaten om in plaats daarvan een knop voor een sidebar te laten zien.

Welke hoeveelheid pixels je gebruikt (je `breakpoint`) hangt af voor of je voor telefoons, tablets of computers wilt werken. Je kunt zoveel `media`-queries toevoegen als je wilt. Populaire `breakpoints` zijn:

- Tot 480px voor telefoons
- Tot 768px voor tablets
- Alles hierbuiten is voor computers/laptops

## Mobile-first
Tegenwoordig is het ook populair om je website eerst voor telefoons te ontwerpen en dan aan te passen voor computers/laptops, in plaats van andersom. Dit heet `Mobile-first` design. Net gebruikten we in de media-queries `max-width`, om tot een bepaalde resolutie iets te doen. Als je heir `min-width` van maakt, doe je vanaf bepaalde resoluties dus iets. Je kunt vervolgens de volgende media-queries maken.

```css
@media only screen and (min-width: 480px) {
  /* CSS voor op tablets */
}
```

en

```css
@media only screen and (min-width: 768px) {
  /* CSS voor op computers/laptops */
}
```

Mobile-first is volgensmij geen verplichting, en als je liever gewoon met computers als hoofddoel werkt heb je dit niet nodig.
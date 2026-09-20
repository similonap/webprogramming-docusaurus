# Webprogramming

Cursusconfiguratie op basis van de onderwerpen en labo’s van BA Web Programming. Alle lesinhoud, oefeningen, starters, oplossingen en vormgeving komen uit de git-submodule `course-material` (de centrale monorepo).

## Starten

Gebruik Node.js 22 of nieuwer, npm en Git.

```bash
npm start
```

De setup haalt automatisch de nieuwste versie van `main` van de monorepo op en installeert de gedeelde dependencies. Daarna worden uitsluitend de geselecteerde documenten naar `.course` samengesteld. Deze gegenereerde map wordt niet bijgehouden in Git.

```bash
npm run build
npm run serve
```

De productiebuild staat in `.course/build`. De starters en oplossingen van de geselecteerde oefeningen worden automatisch als zipbestanden meegebouwd.

## Configuratie

- `sidebars.ts`: expliciete selectie en volgorde van theorie en oefeningen. Er zijn geen automatisch gegenereerde topicselecties.
- `docusaurus.config.ts`: titel, navigatie, URL en buildinstellingen. Stel bij publicatie `COURSE_URL` in op de echte website-URL; lokaal is dit `http://localhost:3000`.
- `config/content.ts`: filters voor onderdelen van gedeelde pagina’s die buiten deze cursus vallen. De oorspronkelijke monorepo-pagina’s blijven ongewijzigd. De build stopt als een verwachte sectie niet meer bestaat.
- `config/exercise-sources.json`: herkomstcontrole voor de 59 geselecteerde oefeningen; dit bestand verschijnt niet op de cursuswebsite.
- `DEKKING.md`: vergelijking en resterende hiaten.
- `vercel.json`: bouwcommando en uitvoermap voor Vercel. Er is nog geen deployment of domein ingesteld.

De eerste TypeScript-pagina is de startpagina. De algemene introductie, projecten en labo-overzichten van Webontwikkeling worden niet gebruikt: die verwijzen naar andere leerstof. De labo’s die EJS gebruiken of daarop voortbouwen zijn uitgesloten. De theoriepagina’s blijven ongewijzigd.

## Werken met de vastgelegde submoduleversie

Deze commando’s halen geen nieuwe bronversie op. Installeer vooraf de dependencies met `npm ci --prefix course-material --include=dev`.

```bash
npm run assemble:local
npm run start:local
npm run build:local
```

`npm start` en `npm run build` blijven, zoals bij Webontwikkeling, altijd de nieuwste bronversie ophalen. Wil je een eerder vastgelegde versie terugzetten, gebruik dan `git submodule update --init --recursive --checkout course-material` en daarna de lokale commando’s.

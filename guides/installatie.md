# Installatie

## Les 1

- [Installatie](#installatie)
  - [Les 1](#les-1)
  - [Les 2](#les-2)
  - [Les 3](#les-3)

Check of node en npm de juiste versie hebben:

`node -v` versie 20 of 22

`npm -v` versie 10

- Installeer node/npm indien nodig: https://nodejs.org/en/download (Scroll naar beneden voor installer van een prebuilt
  versie)

## Les 2

Als het goed is heb je alle vereisten al om met Expo te werken.

Maak je eerste project aan door het volgende commando uit te voeren (vervang `newproject` voor de naam van jouw
project):

`npx create-expo-app newproject --template blank`

Update bij problemen eerst je npm: `npm install -g npm@latest`

Open het zojuist aangemaakte project in PhpStorm. Daarna kun je de app bekijken met de Expo Go app op je telefoon, door
in de terminal van je project het volgende uit te voeren:

`npm run start`

**Let op!** Je telefoon moet verbonden zijn met hetzelfde netwerk als je computer.

[Expo Go App en simulator opties](https://docs.expo.dev/get-started/set-up-your-environment/)

## Les 3

Omdat de documentatie van de installatie van een navigator verdeeld is over meerdere pagina's, en ook diverse extra
modules in de documentatie gebruikt worden, vind je hier een overzicht van de essentiële stappen:

**basis navigation** (altijd nodig)

```
npm install @react-navigation/native
npx expo install react-native-screens react-native-safe-area-context
```

**type navigator** (kies één van onderstaande navigators)

- `npm install @react-navigation/stack`, of
- `npm install @react-navigation/native-stack`, of
- `npm install @react-navigation/bottom-tabs`

**implementatie**

Daarna kan je de navigator implementeren. Volg daarvoor de stappen uit ['Hello React Navigation'](https://reactnavigation.org/docs/hello-react-navigation#creating-a-native-stack-navigator), vanaf 'Creating a
Native Stack Navigator'. Je kunt bij de code voorbeelden steeds kiezen tussen **static**, vergelijkbaar met routing bij
PRG6, of **dynamic**, waarbij de configuratie in de `JSX` plaatsvindt.

> We raden sterk aan om de optie **dynamic** te kiezen. Hiermee kun je namelijk props meegeven aan je componenten, iets
> wat je waarschijnlijk nodig zult hebben.

NB. De handleiding is voor een `Native Stack Navigator`, dus als je voor een ander type navigator gekozen hebt moet je
dat niet vergeten zelf aan te passen.

https://reactnavigation.org/docs/hello-react-navigation#creating-a-native-stack-navigator (static)<br>
https://reactnavigation.org/docs/hello-react-navigation/?config=dynamic#creating-a-native-stack-navigator (dynamic)<br>

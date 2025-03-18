# Les 5

- [Les 5](#les-5)
  - [Maps](#maps)
  - [Location](#location)
    - [Coarse Location (`LocationAccuracy.Low`)](#coarse-location-locationaccuracylow)
    - [Fine Location (`LocationAccuracy.High`)](#fine-location-locationaccuracyhigh)
    - [Locatie-app testen](#locatie-app-testen)
  - [Opdracht 5.1](#opdracht-51)
  - [Opdracht 5.2](#opdracht-52)
  - [Eindopdracht](#eindopdracht)

<br><br>

## Maps

React Native biedt ondersteuning voor het gebruik van kaarten in apps. Afhankelijk van het platform wordt automatisch de
juiste kaartendienst gekozen:

- Google Maps voor Android
- Apple Maps voor iOS

Met Expo Go is het mogelijk om kaarten te gebruiken zonder een API-key te configureren tijdens development. Voor een
productie-app is dit wel nodig.

Je hebt de componenten [MapView](https://docs.expo.dev/versions/latest/sdk/map-view/) en
[Marker](https://github.com/react-native-maps/react-native-maps) nodig om met maps te werken.

<br><br>

## Location

Mobiele apparaten kunnen hun locatie op verschillende manieren bepalen.

### Coarse Location (`LocationAccuracy.Low`)

Maakt gebruik van wifi-netwerken, mobiele zendmasten en IP-adressen. Dit is minder nauwkeurig (vaak binnen enkele
honderden meters), maar wel sneller en verbruikt minder energie en heeft dus een lager batterijverbruik. Gebruik dit als
nauwkeurigheid niet zo belangrijk is, bijvoorbeeld voor een weer-app.

### Fine Location (`LocationAccuracy.High`)

Hierbij wordt de GPS gebruikt, vaak in combinatie met andere sensoren op de telefoon (zoals gyroscoop en kompas). Dit
zorgt voor een zeer nauwkeurige plaatsbepaling (tot op enkele meters), maar heeft daardoor ook een hoger
batterijverbruik. Gebruik dit dus alleen als je echt precies moet weten waar iemand is, bijvoorbeeld voor een
navigatie-app.

### Locatie-app testen

Om een locatie-app te testen zonder steeds naar buiten te hoeven, kan je gebruik maken van de opties in de Android
Emulator (Extended controls - Location) of iOS simulator (Features - Location). Ook is het mogelijk om op een Android
device een app te installeren om een fake locatie in te stellen.

- Huidige locatie ophalen: https://docs.expo.dev/versions/latest/sdk/location/
- Accuracy van locatie ophalen: https://docs.expo.dev/versions/latest/sdk/location/#locationoptions

<br><br>

## Opdracht 5.1

Toon een kaart met in het midden de locatie van ons schoolgebouw (Wijnhaven 99) en zoom daarop in. Toon ook de huidige
locatie van de gebruiker (Tip: dit kan direct via de `MapView`).

(MapView)[https://github.com/react-native-maps/react-native-maps/blob/master/docs/mapview.md]

<br><br>

## Opdracht 5.2

Zorg nu dat de kaart automatisch de kaart centreert op de locatie van de gebruiker, ook als de gebruiker beweegt. Laat
met een spoor van markers zien waar de gebruiker is geweest als de gebruiker beweegt.

Nuttige links:
[watchPositionAsync](https://docs.expo.dev/versions/latest/sdk/location/#locationwatchpositionasyncoptions-callback)

<br><br>

## Eindopdracht

Uitleg en start eindopdracht.

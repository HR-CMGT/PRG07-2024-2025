# Les 3

- [Les 3](#les-3)
  - [Navigatie in React Native](#navigatie-in-react-native)
    - [Stack Navigator en Native Stack Navigator](#stack-navigator-en-native-stack-navigator)
    - [Bottom Tabs Navigator](#bottom-tabs-navigator)
  - [Lijsten in React Native](#lijsten-in-react-native)
    - [List Views](#list-views)
  - [Opdracht 3.1 - Navigeren tussen twee schermen](#opdracht-31---navigeren-tussen-twee-schermen)
  - [Opdracht 3.2 - Navigeren vanuit een statische lijst](#opdracht-32---navigeren-vanuit-een-statische-lijst)
  - [Opdracht 3.3 - Navigeren vanuit een dynamische lijst](#opdracht-33---navigeren-vanuit-een-dynamische-lijst)

<br><br>

## Navigatie in React Native

In React Native werkt navigatie anders dan in een browser. Er zijn geen URL’s zoals op het web, maar in plaats daarvan
gebruik je schermen. Elk scherm heeft een naam, en je kunt daartussen navigeren.

Bij navigeren kun je ook **data meegeven**. Bijvoorbeeld: als je een lijst met producten hebt, kun je bij een klik op
een product de details doorsturen naar het volgende scherm.

### Stack Navigator en Native Stack Navigator

Een `Stack Navigator` (`Native Stack Navigator`) werkt als een stapel schermen, waarbij alleen het bovenste scherm
zichtbaar is voor de gebruiker. Wanneer je naar een nieuw scherm gaat, wordt dit **bovenop de stapel** geplaatst. Het
vorige scherm blijft eronder staan en verdwijnt niet uit het geheugen. Wanneer je op de terug-knop drukt, dan wordt het
bovenste scherm **weggehaald** en zie je dus weer het vorige scherm.

Dit is vergelijkbaar met hoe een browsergeschiedenis werkt: als je een nieuwe pagina opent, kun je met de terug-knop
weer naar de vorige pagina. <br> https://reactnavigation.org/docs/stack-navigator<br>
https://reactnavigation.org/docs/native-stack-navigator

### Bottom Tabs Navigator

Een `Bottom Tabs Navigator` maakt een navigatiebalk onderin het scherm met tabbladen. Dit zie je vaak in apps zoals
Instagram of WhatsApp. Binnen elke tab zou je weer een Stack Navigator kunnen gebruiken als er binnen die tab tussen
verschillende schermen genavigeerd moet worden. <br> https://reactnavigation.org/docs/bottom-tab-navigator

<br><br>

## Lijsten in React Native

Een mobiele app heeft **geen oneindig groot scherm** en ook geen standaard scrollbar zoals in een webbrowser. Als je
meer content wilt tonen dan op het scherm past, moet je zelf zorgen voor scroll-functionaliteit, bijvoorbeeld met een
`ScrollView`.

Een `ScrollView` maakt scrollen mogelijk en werkt prima voor bijvoorbeeld tekstpagina’s. Maar als je een lijst met een
onbekend aantal items wilt tonen, is een `ScrollView` minder geschikt. Dit komt omdat een `ScrollView` **alle** items
in één keer laadt, zelfs als ze niet zichtbaar zijn. Bij lange lijsten kan dit veel geheugen verbruiken en je app
trager maken. De oplossing hiervoor is om gebruikt maken van een `List View`.

### List Views

Een `List View` is een geoptimaliseerde manier om lijsten weer te geven. In tegenstelling tot een `ScrollView` laadt
een List View alleen de items in die op dat moment op het scherm zichtbaar zijn. Dit maakt het efficiënter en voorkomt
onnodig geheugenverbruik.

React Native biedt twee soorten List Views:

- **`FlatList`** → Het standaardcomponent voor het weergeven van een lijst met items.
- **`SectionList`** → Voor een lijst met gegroepeerde items, zoals een alfabetische lijst met secties per letter.

https://reactnative.dev/docs/scrollview<br> https://reactnative.dev/docs/using-a-listview

<br><br>

## Opdracht 3.1 - Navigeren tussen twee schermen

[Installeer](../guides/installatie.md#les-2) een nieuwe Expo app. <br>

[Installeer](../guides/installatie.md#les-3) een **Stack Navigator**.<br>

Bouw een React Native-app met twee schermen en gebruik de **Stack Navigator** om ertussen te navigeren. []

**Functionaliteiten**

- **Scherm 1** bevat een **counter** en een **button** om de waarde van de counter te verhogen.
- Daarnaast bevat **scherm 1** ook een **button** die **scherm 2** opent.
- Wanneer je naar **scherm 2** navigeert, wordt de **huidige waarde van de counter** als parameter meegestuurd.
- Op **scherm 2** wordt deze waarde weergegeven.

<br><br>

## Opdracht 3.2 - Navigeren vanuit een statische lijst

[Installeer](../guides/installatie.md#les-2) een nieuwe Expo app. <br> Bouw een React Native-app met twee schermen en
een **statische lijst** met gegevens op het eerste scherm. Gebruik een **Stack Navigator** om tussen de twee schermen
te navigeren.

**Functionaliteiten**

- Maak of genereer een lijst met gegevens over een onderwerp naar keuze.
- Toon op **scherm 1** de gegevens in een `FlatList`.
- Wanneer de gebruiker op een item drukt wordt **scherm 2** geopend, waarbij de details van het geselecteerde item als
  **parameter** worden meegegeven.
- Geef de ontvangen gegevens weer op **scherm 2**.

<br><br>

## Opdracht 3.3 - Navigeren vanuit een dynamische lijst

[Installeer](../guides/installatie.md#les-2) een nieuwe Expo app. <br> Bouw een React Native-app met twee schermen en
een lijst met notes of chess spots op het eerste scherm. Gebruik een **Stack Navigator** om tussen de twee schermen te
navigeren.

**Functionaliteiten**

- Haal de [notes](https://notes.basboot.nl/notes) of [chess spots](https://prg06-node-express.antwan.eu/spots/) op van
  de webservice.
  - Laat tijdens het ophalen van de data een loader zien met `ActivityIndicator` (Tip: de notes webservice ondersteunt
    een header `x-delay-ms` waarmee je de response een aantal milliseconden kunt vertragen)
- Toon op **scherm 1** de gegevens in een `FlatList`.
- Wanneer de gebruiker op een item drukt moet **scherm 2** geopend worden.
- Haal op **scherm 2** de details op van de geselecteerde note of chess spot en toon deze op het scherm.

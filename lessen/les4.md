# Les 4

- [Les 4](#les-4)
  - [Persistent data](#persistent-data)
  - [Gebruikersinvoer](#gebruikersinvoer)
  - [Opdracht 4.1 - Light/dark mode \& AsyncStorage](#opdracht-41---lightdark-mode--asyncstorage)
  - [Opdracht 4.2 - Settings \& AsyncStorage](#opdracht-42---settings--asyncstorage)
  - [Opdracht 4.3 - CRUD](#opdracht-43---crud)

<br><br>

## Persistent data

In mobiele apps is het soms nodig om gegevens lokaal op te slaan, bijvoorbeeld gebruikersvoorkeuren of een inlogsessie.

**AsyncStorage** is een eenvoudige key-value opslagmethode voor het opslaan van gegevens die tussen app-sessies behouden
moeten blijven. Het is vergelijkbaar met localStorage in de browser, maar werkt asynchroon en ondersteunt grotere
hoeveelheden data. <br> https://docs.expo.dev/versions/latest/sdk/async-storage/

Voor gevoelige gegevens, zoals wachtwoorden of tokens, kan je beter **Expo Secure Storage** gebruiken. Dit slaat
gegevens versleuteld op en maakt gebruik van de beveiligde opslagmechanismen van het besturingssysteem (bijv. de
Keystore op Android en de Keychain op iOS). Ook deze storage werkt asynchroon. <br>
https://docs.expo.dev/versions/latest/sdk/securestore/

Omdat deze opslagmechanismen alleen strings accepteren, moeten complexe gegevens eerst worden omgezet naar een string
met `JSON.stringify()`. Bij het ophalen kan je dan `JSON.parse()` gebruiken om het oorspronkelijke dataformaat weer
terug te krijgen.

<!--

AsyncStorage
AsyncStorage.setItem('my-key', value) / getItem('my-key);
Alleen stringdata => stringify

Expo Secure Storage
https://docs.expo.dev/versions/latest/sdk/securestore/

Standaard config is genoeg om als storage te gebruiken

SecureStore.setItemAsync(key, value);
SecureStore.getItemAsync(key);
-->

<br><br>

## Gebruikersinvoer

In React Native werkt gebruikersinvoer met formulieren op een vergelijkbare manier als in de normale React. Je gebruikt
state-variabelen om de ingevoerde waarden op te slaan. Hiervoor gebruik je het component `TextInput`.

Een `TextInput` accepteert standaard één regel aan tekstinvoer, zoals je gewend bent van de `<input>` in HTML, maar je
kunt het gedrag aanpassen:

- **Numeriek toetsenbord**: Gebruik `keyboardType="numeric"` als er alleen getallen ingevoerd moeten worden
  (vergelijkbaar in HTML met `<input type="number">`)
- **Meerdere regels**: Stel `multiline={true}` in om invoer over meerdere regels toe te staan (vergelijkbaar in HTML met
  een `<textarea>`).

<br>

Op mobiele apparaten kan het toetsenbord over invoervelden heen vallen. Om dit te voorkomen, gebruik je een
`KeyboardAvoidingView`.

<br><br>

## Opdracht 4.1 - Light/dark mode & AsyncStorage

Zorg dat de keuze tussen light en dark mode van [opdracht 2.6](./les2.md#opdracht-26---dark-mode) bewaard blijft, ook
als de app afgesloten en opnieuw opgestart wordt.

Nuttige links: [AsyncStorage](https://docs.expo.dev/versions/latest/sdk/async-storage/)

<br><br>

## Opdracht 4.2 - Settings & AsyncStorage

Bouw een React Native-app met **twee schermen** en gebruik de **Standaard Stack Navigator** (`npm install @react-navigation/stack`).
Het tweede scherm is een **settingsscherm** waarin de gebruiker een naam en een leeftijd kan invoeren. Deze gegevens moeten
vervolgens worden weergegeven op het eerste scherm.

**Deel 1**

- **Scherm 1** toont in eerste instantie de melding `Nog niet alle gegevens zijn bekend.` wanneer er nog geen settings
  bekend zijn in dat scherm.
- Voeg in de **header** aan de rechterkant een knop toe met de tekst `Settings`, die **scherm 2** opent.
- **Scherm 2** bevat twee **invoervelden** om een naam en een leeftijd in te voeren. Zorg ervoor dat het invoerveld voor
  de leeftijd een numeriek veld is, zodat er alleen cijfers ingevoerd kunnen worden. Tot slot bevat dit scherm de knop
  **Opslaan**.
- Na drukken op de knop **Opslaan** moet je terug navigeren naar **scherm 1**, waarbij de naam en leeftijd als
  parameters meegestuurd moeten worden.
  - Let op: standaard wordt er ook een back button getoond links in de header. Wanneer hierop wordt gedrukt hoeven de
    settings niet te worden meegestuurd, dus alleen wanneer op de knop **Opslaan** wordt gedrukt.
- Toon op **scherm 1** de tekst `Hallo [NAAM], jij bent [LEEFTIJD] jaar oud.`, waarbij de placeholders vervangen moeten
  worden door de ingevoerde settings.

  Nuttige links: [Header buttons](https://reactnavigation.org/docs/header-buttons/),
  [TextInput](https://reactnative.dev/docs/textinput),
  [Passing params to a previous screen](https://reactnavigation.org/docs/params/#passing-params-to-a-previous-screen),
  [KeyboardAvoidingView](https://reactnative.dev/docs/keyboardavoidingview),
  [SafeArea](https://docs.expo.dev/versions/latest/sdk/safe-area-context/)

<br>

**Deel 2**

- De settings worden nu op **scherm 1** getoond, maar wanneer je de app opnieuw opstart dan zijn deze settings weer weg.
  Zorg er daarom voor dat deze worden opgeslagen in de **AsyncStorage**, zodat ze ook na een herstart van de app worden
  getoond op **scherm 1**.
- Zorg er ook voor dat bij het openen van **scherm 2** de invoervelden worden ingevuld met de gegevens uit de
  **AsyncStorage**.

<br>

**Deel 3: Extra opdracht**

- Toon de leeftijden in een Picker. Je moet kunnen kiezen uit de leeftijd 0 t/m 100.
- Voeg op het settingsscherm ook de mogelijkheid toe om te switchen tussen light en dark mode en sla dit op in de
  AsyncStorage. Zorg er daarbij voor dat alle kleuren op basis van de mode worden aangepast, ook die van de navigatie.
  Dit kan je doen met lifting state up en prop drilling, of met de Context API.

Nuttige links: [React Navigation Themes](https://reactnavigation.org/docs/themes/),
[Picker](https://github.com/react-native-picker/picker) (AutoLinking is niet nodig)

<br>

## Opdracht 4.3 - CRUD

Ga verder met je code van [opdracht 3.3](./les3.md#opdracht-33-navigeren-vanuit-een-dynamische-lijst). Voeg daaraan een
Create, Update en Delete toe. Zorg er met een `KeyboardAvoidingView` en een `ScrollView` voor dat er geen velden
verstopt zitten achter het toetsenbord van je telefoon.

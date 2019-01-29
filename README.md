# Travel Planning App

> Made with React Native and GraphQL

## To run in iOS simulator

```
$ npm install
$ react-native link react-native-gesture-handler
$ react-native link react-native-vector-icons
$ react-native run-ios
```

**GraphQL**:

We use [Graphcool](https://www.graph.cool/) for prototyping. The Graphcool service is deployed to this endpoint: [https://api.graph.cool/simple/v1/cjrh62bkka7l501132k2sp85b](https://api.graph.cool/simple/v1/cjrh62bkka7l501132k2sp85b)

To learn more about GraphQL:
* How to GraphQL: https://www.howtographql.com/
* ReactNative GraphQL Graphcool [starter project](https://github.com/graphcool-examples/react-native-graphql/tree/master/quickstart-with-apollo)
* [GraphQL Schema](https://www.apollographql.com/docs/apollo-server/essentials/schema.html)
* Schema Definition Language [official doc](https://graphql.org/learn/schema/#type-language)

## Product Specification

__App Name__:   Travel Japan

__App Description__:   This app provides a list of things to do for you and your friends traveling together in Japan. You can add up to 3 people to your travel group. Pick which date to start your trip and also how long you plan to stay in Japan. Let the app take care of the rest of the planning

__Additional Info__:
This App is for planning a trip with your friends. It gives you:

* Access to your itinerary via calendar view
* Access to your list of planned activities
* An integrated to-do-list and a map for the area
* A quick lookup on the stuff you researched, including travel destination articles and translations for words from the local language to English

![Travel Japan on App Store](https://github.com/xiaoyunyang/react-native-travel-app/blob/2017-archive/docs/appStore.png?raw=true)

Download Link on App Store:
[https://itunes.apple.com/us/app/travel-japan/id1260677523?mt=8](https://itunes.apple.com/us/app/travel-japan/id1260677523?mt=8)

## Dev Information

### Running the app

* Install ReactNative on your computer - [React Native Tutorial from Facebook](https://facebook.github.io/react-native/releases/next/docs/getting-started.html)
* Fork the project, then download the project from Github
* run `npm install`
* To run on simulator, In the terminal: `react-native run-ios`
* Go to the ios folder and click on the .xcodeproj file to open the project in Xcode
*  Running on Devices: [Read the Facebook doc](https://facebook.github.io/react-native/docs/running-on-device.html)
* The error where Xcode requires a development team - [tutorial](https://stackoverflow.com/questions/37806538/code-signing-is-required-for-product-type-application-in-sdk-ios-10-0-stic)

### Components

``ActivityList``

* A ListView of all the activities planned for the trip/event.

``MyList``

* ``ActivityList`` with a search and tag filters. The search and tag filters are custom functions in the ``MyList`` component.

``Calendar``

* ``ActivityList`` with a calendar filter. The calendar filter is a ``Carousel`` component.

### Access Data for The App

The Data used to generate to App is stored here: [japan.json](https://github.com/xiaoyunyang/JapanApp/blob/master/data/japan.json)

[japan.json](https://github.com/xiaoyunyang/JapanApp/blob/master/data/japan.json) contains `FIELDS`, which is an array of objects:

```javascript
"FIELDS": [
  {
    "id": 0,
    "title":"Arrive at Haneda Airport",
    "subtitle": "Yay Japan!",
    "tags": ["Xiaoyun", "Andrew", "Kyle"],
    "active": true,
    "date": "Mon Aug 07 2017",
  }, {
    "id": 1,
    "title":"Check into Ginza Bay Capsule Hotel",
    "subtitle": "Ginza is an area in Tokyo with a lot of shopping",
    "tags": ["Xiaoyun", "Andrew", "Kyle"],
    "active": true,
    "date": "Mon Aug 07 2017",
  }
]
```

[detail.json](https://github.com/xiaoyunyang/JapanApp/blob/master/data/detail.json) is a set of objects that looks like this:

```javascript
{
  "0": {
    "todo": "Take the Keiyu-Kuko (red) Line to Higashi-ginza Station (where the capsule hotel is)",
    "image": "none",
    "link": "none",
    "markers": [
      {
        "title": "Haneda Airport",
        "coordinate": {"latitude": 35.549358, "longitude": 139.779839}
      }, {
        "title": "Metro Station",
        "coordinate": {"latitude": 35.544854, "longitude": 139.767124}
      }
    ]
  },
  "1": {
    "todo": "Check in the the hotel",
    "image": "none",
    "link": "none",
    "markers": [
      {
        "title": "Tokyo Ginza Bay Hotel",
        "coordinate": {"latitude": 35.667492, "longitude": 139.763868}
      }
    ]
  },
  ...
}
```

The `Details` component gets data from [detail.json](https://github.com/xiaoyunyang/JapanApp/blob/master/data/detail.json):

![Details Page](https://github.com/xiaoyunyang/react-native-travel-app/blob/2017-archive/docs/detailsPage.png?raw=true)

## TODO
- [ ] Allow to play sound in Translator


## Dependencies:
Before You start react-native run-ios in terminal, install the dependencies:

##### React Navigator
* [React Native Tab Navigator](https://github.com/expo/react-native-tab-navigator)
* [React Native Material Bottom Navigation](https://www.npmjs.com/package/react-native-material-bottom-navigation) -  A helper component to the Tab Navigator:
* [TabNavigator main API](https://reactnavigation.org/docs/navigators/tab)
* [React Navigation Examples](https://github.com/react-community/react-navigation/tree/master/examples/NavigationPlayground/js)
* In the terminal

 ```
 npm install react-native-tab-navigator --save
 npm install react-native-material-bottom-navigation --save
 ```

##### Dependencies

* [React Navigation](https://reactnavigation.org/docs/en/getting-started.html)
* [react-native-vector-icons](https://github.com/oblador/react-native-vector-icons) - comes with [buncled icon sets](https://github.com/oblador/react-native-vector-icons#bundled-icon-sets). We use [ionicons](https://ionicons.com/).
* [React Native Carousel](https://github.com/nick/react-native-carousel)
* [react-native-swipeout](https://github.com/dancormier/react-native-swipeout)
* [react-native-maps](https://github.com/airbnb/react-native-maps) by Airbnb
* [redux-persist](https://github.com/rt2zz/redux-persist)
* [react-native-date-picker](https://github.com/xgfe/react-native-datepicker)
* [NativeBase](https://nativebase.io/docs/v0.3.0/components#button) - Consider using this in an update to the app to pretty up the UI.
* [react-native-fetch-blob](https://github.com/wkh237/react-native-fetch-blob) - How to install: [read this](https://github.com/wkh237/react-native-fetch-blob/issues/84)

### Useful Resources:
* Tutorial and API - [React Native Tutorial from Facebook](https://facebook.github.io/react-native/releases/next/docs/getting-started.html)
* Stackoverflow - [How to increment JS Date](https://stackoverflow.com/questions/3674539/incrementing-a-date-in-javascript)
* API - [JavaScript Date](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Date)
* Material Design Icons - [Materials Icon](https://material.io/icons/)
* Pretty Good Tutorial for Navigation - [The Tutorial](https://mentormate.com/blog/react-native-components/)
* How to import custom Fonts into Xcode project - [The Tutorial](http://codewithchris.com/common-mistakes-with-adding-custom-fonts-to-your-ios-app/)
* How to manage Local assets - [The Tutorial](https://willowtreeapps.com/ideas/react-native-tips-and-tricks-2-0-managing-static-assets-with-absolute-paths/)
* React Native App that reads and writes to a text file: [The Tutorial](http://moduscreate.com/react_native_custom_components_ios/)
* [Realm](https://realm.io/docs/javascript/latest/index.html) - Persistent Data Layer for React Native.
* Database for maps in its own vector format, MWM: [The Map Database](http://direct.mapswithme.com/direct/latest/)
* Wrapping the app in Redux, this tutorial is very helpful:  [Jon Lebenshold's Medium Article](https://medium.com/@jonlebensold/getting-started-with-react-native-redux-2b01408c0053)
* How to change the name of your app: [Good Tutorial on Medium](https://medium.com/the-react-native-log/how-to-rename-a-react-native-app-dafd92161c35)
* Why Apple rejects app submittals: [Official FAQ](https://developer.apple.com/app-store/review/rejections/), [11 Reasons](http://www.moveoapps.com/blog/11-reasons-why-apple-will-reject-your-app-when-submitted-for-review/)
* Import and Export Modules in Javascript: Read [This Article](https://medium.com/@trekinbami/a-not-so-in-depth-explanation-of-es6-modules-import-and-export-13a80300f2f0)
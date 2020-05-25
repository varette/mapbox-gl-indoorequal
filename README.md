# Mapbox-gl-indoorequal ![build](https://img.shields.io/github/workflow/status/indoorequal/mapbox-gl-indoorequal/CI) [![npm](https://img.shields.io/npm/v/mapbox-gl-indoorequal)](https://www.npmjs.com/package/mapbox-gl-indoorequal)

mapbobx-gl-indoorequal is a mapbox-gl.js plugin to display indoor data from [indoor=][].

It provides:

-   a level control to change the level displayed on the map
-   a programatic API to change the level displayed

[**See the demo**](https://indoorequal.github.io/mapbox-gl-indoorequal).

![](./demo.gif)

## Install

**With NPM**

    npm install --save mapbox-gl-indoorequal

**In the browser**

```html
<script src="https://unpkg.com/mapbox-gl-indoorequal@latest/dist/mapbox-gl-indoorequal.umd.min.js"></script>
<link href="https://unpkg.com/mapbox-gl-indoorequal@latest/mapbox-gl-indoorequal.css" rel="stylesheet" />
```

## Example

Get your free key at [indoorequal.com](https://indoorequal.com).

```javascript
import mapboxgl from 'mapbox-gl';
import IndoorEqual from 'mapbox-gl-indoorequal';
import 'mapbox-gl-indoorequal/mapbox-gl-indoorequal.css';

const map = new mapboxgl.Map({
  container: 'map',
  style: 'mapbox://styles/mapbox/traffic-night-v2',
  center: [2.3601072, 48.876853],
  zoom: 18
});

const indoorEqual = new IndoorEqual(map, { apiKey: 'mykey' });
map.addControl(indoorEqual);
```

## API

<!-- Generated by documentation.js. Update this documentation by updating the source code. -->

#### Table of Contents

-   [IndoorEqual](#indoorequal)
    -   [Parameters](#parameters)
    -   [Properties](#properties)
    -   [on](#on)
        -   [Parameters](#parameters-1)
    -   [off](#off)
        -   [Parameters](#parameters-2)
    -   [onAdd](#onadd)
    -   [onRemove](#onremove)
    -   [updateLevel](#updatelevel)
        -   [Parameters](#parameters-3)
-   [IndoorEqual#levelschange](#indoorequallevelschange)
-   [IndoorEqual#levelchange](#indoorequallevelchange)

### IndoorEqual

Load the indoor= source and layers in your map.

#### Parameters

-   `map` **[object](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Object)** the mapbox-gl instance of the map
-   `options` **[object](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Object)**  (optional, default `{}`)
    -   `options.url` **[url](https://developer.mozilla.org/docs/Web/API/URL/URL)?** Override the default tiles URL (<https://tiles.indoorequal.org/>).
    -   `options.apiKey` **[string](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/String)?** The API key if you use the default tile URL (get your free key at [indoorequal.com](https://indoorequal.com)).

#### Properties

-   `level` **[string](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/String)** The current level displayed
-   `levels` **[array](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Array)** The levels that can be displayed in the current view

Returns **[IndoorEqual](#indoorequal)** `this`

#### on

Add an event listener

##### Parameters

-   `name` **[string](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/String)** the name of the event
-   `fn` **[function](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Statements/function)** the function to be called when the event is emitted

#### off

Remove an event listener.

##### Parameters

-   `name` **[string](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/String)** the name of the event
-   `fn` **[function](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Statements/function)** the same function when on() was called

#### onAdd

Add the level control to the map
Used when adding the control via the map instance: map.addControl(indoorEqual)

#### onRemove

Remove the level control
Used when removing the control via the map instance: map.removeControl(indoorEqual)

#### updateLevel

Update the displayed level.

##### Parameters

-   `level` **[string](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/String)** the level to be displayed

### IndoorEqual#levelschange

Emitted when the list of available levels has been updated

Type: [array](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Array)

### IndoorEqual#levelchange

Emitted when the list of available levels has been updated

Type: [string](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/String)

## Develop

### Run tests

    yarn test

### Build a new version

    yarn build

### Generate the documentation

    yarn doc

## License

GNU AGPL v3

[indoor=]: https://indoorequal.org/

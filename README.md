# Mapbox GL JS Infobox

Adds an infobox and/or gradient switch to `mapbox-gl`

## Installation:

```bash
npm i mapbox-gl-infobox --save
```

## Usage:

```ts
import { MapboxGradientBoxControl, MapboxInfoBoxControl } from "mapbox-gl-infobox";
import { Map as MapboxMap } from "mapbox-gl";

import "mapbox-gl-infobox/styles.css";

const map = new MapboxMap();
map.addControl(new MapboxGradientBoxControl());
map.addControl(new MapboxInfoBoxControl());
```

## Options:
You can also supply your own options.

```ts
const layerId = "features";
const minMaxValues = {minValue: 0, maxValue: 100};
const weightGetter = properties => properties ? properties['weight'] : 0;
const gradientOptions: MapboxGradientBoxOptions = {
    layerId,
    minMaxValues,
    weightGetter
};
map.addControl(new MapboxGradientBoxControl(gradientOptions));

const formatter = properties => properties ? `<b>Name:</b> ${properties['name']}` : '';
const infoboxOptions: MapboxInfoBoxOptions = {
    layerId,
    formatter
};
map.addControl(new MapboxInfoBoxControl(infoboxOptions));
```

## Screenshots

![Closed](assets/hover.png)
﻿
<!-- TABLE OF CONTENTS -->
<details open="open">
  <summary><h2 style="display: inline-block">Table of Contents</h2></summary>
  <ol>
    <li>
      <a href="#about-the-project">About The Project</a>
      <ul>
        <li><a href="#built-with">Built With</a></li>
      </ul>
    </li>    
    <li><a href="#examples">Examples</a></li>
    <li>
      <a href="#getting-started">Getting Started</a>
      <ul>
        <li><a href="#prerequisites">Prerequisites</a></li>
        <li><a href="#installation">Installation</a></li>
      </ul>
    </li>
    <li><a href="#usage">Usage</a></li>
    <li><a href="#roadmap">Roadmap</a></li>
    <li><a href="#contributing">Contributing</a></li>
    <li><a href="#license">License</a></li>
    <li><a href="#contact">Contact</a></li>
    <li><a href="#acknowledgements">Acknowledgements</a></li>
  </ol>
</details>



<!-- ABOUT THE PROJECT -->
## About The Project

[![Product Name Screen Shot][product-screenshot]](https://techjb.github.io/Vector-Tiles-Google-Maps/examples/basic.html)


A JavaScript library that render Vector Tiles in Google Maps.

This library has been developed to render vector tiles in Google Maps. It has been used the library [Leaflet.MapboxVectorTile](https://github.com/SpatialServer/Leaflet.MapboxVectorTile)
as a start point. The library contains funcionality to provide cache, feature filters, feature styles, onclick event, and show/hide layers.

Further work would be to load [Mapxbox GL Styles](https://docs.mapbox.com/mapbox-gl-js/style-spec/) in Google Maps.

### Built With

* [Maps JavaScript API](https://developers.google.com/maps/documentation/javascript/overview?)
* [Mapbox Vector Tiles](https://github.com/mapbox/vector-tile-js)
* [Protocol Buffers](https://github.com/protocolbuffers/protobuf)
* JavaScript


<!-- DEMO EXAMPLES -->
## Examples

* [Basic](https://techjb.github.io/Vector-Tiles-Google-Maps/examples/basic.html)
* [Cache](https://techjb.github.io/Vector-Tiles-Google-Maps/examples/cache.html)
* [Click](https://techjb.github.io/Vector-Tiles-Google-Maps/examples/click.html)
* [Filter](https://techjb.github.io/Vector-Tiles-Google-Maps/examples/filter.html)
* [Layers](https://techjb.github.io/Vector-Tiles-Google-Maps/examples/layers.html)
* [Styles](https://techjb.github.io/Vector-Tiles-Google-Maps/examples/styles.html)
* [Point, linestring and polygon](https://techjb.github.io/Vector-Tiles-Google-Maps/examples/point-linestring-polygon.html)


<!-- GETTING STARTED -->
## Getting Started

To get a local copy up and running follow these simple steps.

### Prerequisites

This is an example of how to list things you need to use the software and how to install them.
* npm
  ```sh
  npm install npm@latest -g
  ```

### Installation

1. Clone the repo
   ```sh
   git clone https://github.com/techjb/Vector-Tiles-Google-Maps.git
   ```
2. Install NPM packages
   ```sh
   npm install
   ```



<!-- USAGE EXAMPLES -->
## Usage

You create the `MVTSource` object and then insert to as a `overlayMapType`. 
Provide the vector tiles server url throught the options parámeter.


```js
var options = {
    url: "your_vector_tiles_url/{z}/{x}/{y}.pbf"
};

var mvtSource = new MVTSource(map, options);
map.overlayMapTypes.insertAt(0, mvtSource);
```

It is reccomended to load the overlayMapType after tiles have been loaded for the first time 
to avoid duplicate invocation to `GetTile()`. It has been documented in the [Issuetracker](https://issuetracker.google.com/issues/73335429).

```js
 google.maps.event.addListenerOnce(map, 'tilesloaded', function () {
    map.overlayMapTypes.insertAt(0, mvtSource);
});
```

<!-- ROADMAP -->
## Roadmap

See the [open issues](https://github.com/techjb/Vector-Tiles-Google-Maps/issues) for a list of proposed features (and known issues).



<!-- CONTRIBUTING -->
## Contributing

Contributions are what make the open source community such an amazing place to be learn, inspire, and create. Any contributions you make are **greatly appreciated**.

1. Fork the Project
2. Create your Feature Branch (`git checkout -b feature/AmazingFeature`)
3. Commit your Changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the Branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request



<!-- LICENSE -->
## License

See `LICENSE` for more information.



<!-- CONTACT -->
## Contact

Jesús Barrio - [@techjb](https://twitter.com/techjb)

Project Link: [https://github.com/techjb/Vector-Tiles-Google-Maps](https://github.com/techjb/Vector-Tiles-Google-Maps)


<!-- MARKDOWN LINKS & IMAGES -->
<!-- https://www.markdownguide.org/basic-syntax/#reference-style-links -->

[product-screenshot]: images/screenshot.png
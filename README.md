The geodata in this repository was based on the [Tourismusregionen der Schweiz](https://www.bfs.admin.ch/bfs/de/home/statistiken/kataloge-datenbanken/karten.assetdetail.3382021.html) publication of the Swiss Federal Office of Statistics - 1.1.2017.

## Preparation

The PDF version of the regions was converted to SVG using Inkscape, the region clipping shapes extracted, then converted to GeoJSON using [svg-to-geojson](https://github.com/davecranwell/svg-to-geojson) and the following parameters:

```
var geoJson = svgtogeojson.svgToGeoJson([
        [47.4830, 10.2931],
        [45.4905, 5.5723]
    ], document.getElementsByTagName('svg')[0], 3);     
document.location.href = "http://geojson.io/#data=data:application/json," + encodeURIComponent(JSON.stringify(geoJson));
```

And finally exported from GeoJSON.io - then tweaked and re-exported using QGIS, adding back the numeric cantonal identifiers as seen in the PDF.

*Disclaimer:* It's not super precise. More like a guesstimate, due to all the steps involved. Having a proper export, or at least some help aligning the borders, would be warmly welcomed.

## License

This package is licensed by its maintainers under the Public Domain Dedication
and License.

If you intended to use these data in a public or commercial product, please
check the data sources themselves for any specific restrictions.

The geodata in this repository was based on the [Tourismusregionen der Schweiz](https://www.bfs.admin.ch/bfs/de/home/statistiken/kataloge-datenbanken/karten.assetdetail.3382021.html) publication of the Swiss Federal Office of Statistics - 1.1.2017.

Motivated by a tweet:

>Does anyone have a spatial file definition of the 13 <a href="https://twitter.com/hashtag/tourism?src=hash&amp;ref_src=twsrc%5Etfw">#tourism</a> regions in Switzerland? In a format understood by <a href="https://twitter.com/tableau?ref_src=twsrc%5Etfw">@Tableau</a> (Shapefile, KML, MapInfo, GeoJSON). <a href="https://t.co/A9nPN8KZxC">https://t.co/A9nPN8KZxC</a> <a href="https://twitter.com/StatSchweiz?ref_src=twsrc%5Etfw">@StatSchweiz</a>  <a href="https://twitter.com/OpendataCH?ref_src=twsrc%5Etfw">@OpendataCH</a>  <a href="https://twitter.com/hashtag/opendata?src=hash&amp;ref_src=twsrc%5Etfw">#opendata</a> <a href="https://twitter.com/hashtag/opentourism?src=hash&amp;ref_src=twsrc%5Etfw">#opentourism</a> <a href="https://twitter.com/golliez?ref_src=twsrc%5Etfw">@golliez</a> <a href="https://twitter.com/loleg?ref_src=twsrc%5Etfw">@loleg</a> <a href="https://twitter.com/MikeSchudel?ref_src=twsrc%5Etfw">@MikeSchudel</a></p>&mdash; Quantum (@QuantumBIS) <a href="https://twitter.com/QuantumBIS/status/964459384620404736?ref_src=twsrc%5Etfw">February 16, 2018</a>

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

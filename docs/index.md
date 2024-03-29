# Obsidian Notes

Publish your public notes with MkDocs

## Hello World!

The `index.md` in the `/docs` folder is the homepage you see here.

The folders in `/docs` appear as the main sections on the navigation bar.

The notes appear as pages within these sections. For example, [[Note 1]] in `Topic 1`

![ ](glimbourne.svg)



# Outage Map

<link rel="stylesheet" href="https://unpkg.com/leaflet@1.7.1/dist/leaflet.css" integrity="sha512-xodZBNTC5n17Xt2atTPuE1HxjVMSvLVW9ocqUKLsCC5CXdbqCmblAshOMAS6/keqq/sMZMZ19scR4PsZChSR7A==" crossorigin=""/>
<script src="https://unpkg.com/leaflet@1.7.1/dist/leaflet.js" integrity="sha512-XQoYMqMTK8LvdxXYG3nZ448hOEQiglfqkJs1NOQV44cWnUrBc8PkAOcXy20w0vlaXaVUearIOBhiXZ5V3ynxwA==" crossorigin=""></script>

<style type="text/css">
#map {
    width: 400px;
    height: 400px;
    margin: 0;
}
</style>

<div id="map"></div>

<script type="text/javascript">
  document.addEventListener("DOMContentLoaded", function() {
    var mymap = L.map('map').setView([51.505, -0.09], 13);

    L.tileLayer('assets/img/glimbourne.svg', {
      attribution: '',
      maxZoom: 18,
      id: 'mapbox/streets-v11',
      tileSize: 512,
      zoomOffset: -1,
    }).addTo(mymap);
  })
</script>

Emberstead
Glimbourne
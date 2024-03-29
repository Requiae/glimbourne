# Glimbourne

Blab blab blubba


<link rel="stylesheet" href="https://unpkg.com/leaflet@1.7.1/dist/leaflet.css" integrity="sha512-xodZBNTC5n17Xt2atTPuE1HxjVMSvLVW9ocqUKLsCC5CXdbqCmblAshOMAS6/keqq/sMZMZ19scR4PsZChSR7A==" crossorigin=""/>
<script src="https://unpkg.com/leaflet@1.7.1/dist/leaflet.js" integrity="sha512-XQoYMqMTK8LvdxXYG3nZ448hOEQiglfqkJs1NOQV44cWnUrBc8PkAOcXy20w0vlaXaVUearIOBhiXZ5V3ynxwA==" crossorigin=""></script>

<style type="text/css">
#map {
    width: 100%;
    margin: 0;
    aspect-ratio: 1200/1064;
}
</style>

<div id="map"></div>

<script type="text/javascript">
  document.addEventListener("DOMContentLoaded", function() {
    const bounds = [[0, 0], [1064, 1200]];
    const map = L.map("map", {
        crs: L.CRS.Simple,
        maxBounds: bounds,
        minZoom: 0,
        maxZoom: 3,
    });

    const image = L.imageOverlay("assets/img/glimbourne.svg", bounds).addTo(map);

    L.marker([300, 300], {url: "Topic%201/Note%201"}).bindTooltip("Note 1").on("click", markerOnClick).addTo(map);

    function markerOnClick(e) {
        console.log(e.target.options.url)
        window.location.href = `/glimbourne/${e.target.options.url}`
    }

    map.fitBounds(bounds);

  })
</script>
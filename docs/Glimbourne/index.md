---
hide:
  - toc
---
  [ancient facility]: ../Facilities/Inner%20Citadel%20Facility/

# Glimbourne

!!! quote " "

    More advanced than even Estron, the capital of Aflea, Glimbourne shines as the center of magical and technological development.

Glimbourne is situated on top of a large [ancient facility] uncovered almost two hundred years ago, in the year 1401 AC. The facility's purpose is still mostly unknown but it is assumed it played an important role in cleaning up the aftermath of a catastrophy many aeons ago, the only records of which are in legends. Littered across the rolling hills and forests of the countryside are smaller facilities whose purpose can only be guessed to be to assist the main facility.

The city started of as a mere outpost to ease research into the exposed ruins of the inner citadel. Over time the outpost grew, bringing more scholars who eventually founded an university in the citadel, mercenaries to aid and protect the researchers that wanted to explore the surrounding ruins, merchants and craftsmen eager to sell supplies, and finally nobles who were excited by the technological advancements and funded the further growth of Glimbourne.

## Map

<link rel="stylesheet" href="https://unpkg.com/leaflet@1.9.4/dist/leaflet.css" integrity="sha256-p4NxAoJBhIIN+hmNHrzRCf9tD/miZyoHS5obTRR9BMY=" crossorigin="" />
<script src="https://unpkg.com/leaflet@1.9.4/dist/leaflet.js" integrity="sha256-20nQCchB9co0qIjJZRGuk2/Z9VM+kNiyxNV1lvTlZBo=" crossorigin=""></script>

<style type="text/css">
#leaflet-map {
    width: 100%;
    margin: 0;
    z-index: 0;
    aspect-ratio: 1/1;
}
</style>

<div id="leaflet-map"></div>

<script type="text/javascript">
    document.addEventListener("DOMContentLoaded", function() {
        const bounds = [[0, 0], [1064, 1200]];
        const map = L.map("leaflet-map", {
            crs: L.CRS.Simple,
            maxBounds: bounds,
            minZoom: 0,
            maxZoom: 3,
        });

        const image = L.imageOverlay("../assets/img/glimbourne.svg", bounds).addTo(map);

        map.fitBounds(bounds);

        addMarker("University", "./Glimbourne/Scholar District/University", [629, 535]);

        function markerOnClick(e) {
            console.log(e.target.options.url)
            window.location.href = `/glimbourne/${e.target.options.url}`
        }

        function addMarker(title, url, coordinates) {
            L.marker(coordinates, {url: url}).bindTooltip(title).on("click", markerOnClick).addTo(map);
        }
    })
</script>

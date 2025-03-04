<script>
import { onMount } from 'svelte';
import maplibregl from 'maplibre-gl';
import { Protocol } from 'pmtiles';
import 'maplibre-gl/dist/maplibre-gl.css';

let map; // Declare the map variable here

onMount(async () => {
      let protocol = new Protocol();
      maplibregl.addProtocol("pmtiles",protocol.tile);

      map = new maplibregl.Map({  
          container: 'map',
          zoom: 12,
          center: [7.4244581, 43.7383229],
          style: 'style.json',
          hash: 'map'
      });
});  

</script>

<div id="map" style="height: 90vh;"></div>





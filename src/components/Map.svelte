<script>
  import mapStyles from "./map-styles";

  let container;
  let map;
  let marker;
  let zoom = 12;
  let center = { lat: 59.47047, lng: 17.77391 };

  import { onMount } from "svelte";

  onMount(async () => {
    map = new google.maps.Map(container, {
      zoom,
      center,
      styles: mapStyles,
      disableDefaultUI: true,
      gestureHandling: "none",
      scrollwheel: false,
      navigationControl: false,
      mapTypeControl: false,
      scaleControl: false,
      draggable: false
    });

    marker = new google.maps.Marker({
      position: center,
      map: map,
      title: "Almare Stäket Magasinet"
    });
  });
</script>

<style>
  .map {
    width: 100vw;
    height: 400px;
  }
</style>

<div class="map" bind:this={container} />

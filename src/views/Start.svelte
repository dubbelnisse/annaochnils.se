<script>
  import Nav from "../components/Nav.svelte";
  import Map from "../components/Map.svelte";
  import Speech from "../components/Speech.svelte";
  export let ready;
</script>

<style>
  main {
    text-align: center;
    padding: 0;
    max-width: 240px;
    margin: 0 auto;
  }

  h1 {
    color: #fff;
    text-transform: uppercase;
    font-size: 4em;
    font-weight: 100;
  }

  header {
    background: url("/images/bg.jpg") no-repeat;
    background-size: cover;
    display: flex;
    align-items: center;
    justify-content: center;
    min-height: 600px;
  }

  footer {
    margin: 20px 0;
  }

  @media (min-width: 640px) {
    main {
      max-width: none;
    }
  }
</style>

<svelte:head>
  <script
    defer
    async
    src="https://maps.googleapis.com/maps/api/js?key=AIzaSyAEDvDjNYDR5hcD42lL-n1d4nbI5JjBEJ0&callback=initMap">

  </script>
</svelte:head>

<main>
  <Nav />
  <header>
    <h1>ANNA OCH NILS</h1>
  </header>
  {#if ready}
    <Map />
  {/if}
  <Speech />
  <footer>Anna &hearts; Nils</footer>
</main>

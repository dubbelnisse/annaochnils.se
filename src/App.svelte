<script>
  import Start from "./views/Start.svelte";
  import Login from "./views/Login.svelte";
  import { isLoggedIn } from "./store/";

  export let ready;

  isLoggedIn.useLocalStorage();
</script>

{#if $isLoggedIn}
  <Start {ready} />
{:else}
  <Login />
{/if}

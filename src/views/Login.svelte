<script>
  import { isLoggedIn } from "../store/";

  let answer = "";

  function onChange(event) {
    if (event.keyCode === 13 && answer !== "") {
      submit();
    }
  }

  function submit() {
    if (answer.toLowerCase() === "selma") {
      isLoggedIn.set(true);
    }
  }
</script>

<style>
  main {
    align-items: center;
    background-color: #f5f5f5;
    display: flex;
    height: 100vh;
    justify-content: center;
    text-align: center;
    width: 100vw;
  }
</style>

<main>
  <div>
    <h1>ANNA OCH NILS</h1>
    <p>Vad är vårat barns namn?</p>
    <input
      bind:value={answer}
      on:keydown={onChange}
      placeholder="Vårat barns namn" />
    <button on:click|preventDefault={submit}>VIDARE</button>
  </div>
</main>

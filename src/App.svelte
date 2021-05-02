<script>
  import Board from "./Board.svelte";
  import "global.css";
</script>

<main class="app">
  <h1>Svelte Chess Engine:</h1>
  <Board />
  <div class="outer_wrapper">
    <span>FEN:</span>
    <input placeholder="Enter FEN String" /><button>SET</button>
    <p style="color:red; text-align: center;">Error: Invalid FEN String!</p>
  </div>
</main>

<style>
  .app {
    display: flex;
    align-items: center;
    flex-direction: column;
  }
</style>

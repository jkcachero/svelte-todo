<script>
  export let name;
  import Counter from './Counter.svelte';
  import './style.css';
</script>

<main>
  <h1>Hello {name}!</h1>
  <div class="hello">This is global</div>
  <Counter title="New title 2" />
  <p>Visit the <a href="https://svelte.dev/tutorial">Svelte tutorial</a> to learn how to build Svelte apps.</p>
</main>

<style>
  main {
    text-align: center;
    padding: 1em;
    max-width: 240px;
    margin: 0 auto;
  }

  h1 {
    color: #ff3e00;
    text-transform: uppercase;
    font-size: 4em;
    font-weight: 100;
  }

  @media (min-width: 640px) {
    main {
      max-width: none;
    }
  }
</style>

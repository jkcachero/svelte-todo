<script>
    import { onMount } from "svelte";

  export let title = "Hello world!"
  let counter = 0
  let myText = ''

  $: doubled = counter * 2
  $: {
    console.log('doubled', doubled)
    console.log('counter', counter)
  }

  const todos = [
    {
      id: 1,
      title: 'Get a haircut',
      isComplete: false,
    },
    {
      id: 2,
      title: 'Feed the cat',
      isComplete: true,
    },
    {
      id: 3,
      title: 'Write a book',
      isComplete: false,
    },
  ]

  onMount(() => {
    console.log('Counter mounted')
  })

  function increment() {
    counter += 1
  }
  function decrement() {
    counter -= 1
  }
</script>

<div>
  <h1>{title}</h1>
  <p>Current count: {counter}. Doubled is {doubled}</p>
  {#if counter > 5 && counter <= 10}
    <p>You have passed the 5</p>
  {:else if counter > 10}
    <p>You have passed the 10</p>
  {:else}
    <p>Counter is less 5</p>
  {/if}
  <div>
    <button on:click="{decrement}">Decrement</button>
    <button on:click="{increment}">Increment</button>
  </div>
  <form action="#">
    <input type="text" bind:value="{myText}">
    <div>{myText}</div>
  </form>
  <div>
    <h1 class="hello">This is global</h1>
    <h2>Each</h2>
    {#each todos as {id, title, isComplete}, index (id)}
      <div>
        <input type="checkbox" bind:checked="{isComplete}">
        <span>{index} {title}</span>
      </div>
    {/each}
  </div>
</div>

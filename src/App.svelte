<script lang="ts">
  import { afterUpdate } from 'svelte'
  import logo from './assets/svelte.png'
  import './Tailwind.svelte'
  import Users from './Users.svelte'

  let count = 0

  function incrementCount() {
    count++
  }

  let name = 'Your name'

  $: myFancyName = `✨✨✨ ${name} 🚀🚀🚀`

  afterUpdate(() => {
    console.log('Index updated')
  })
</script>

<main class="bg-red-100 min-h-screen">
  <div class="container mx-auto">
    <img src={logo} alt="Svelte Logo" />
    <h1>Svelte 101</h1>
    <ul>
      <li>Markup</li>
      <li>Style</li>
      <ul>
        <li>Global</li>
        <li>Local</li>
      </ul>
      <li>Script</li>
      <ul>
        <li>State</li>
        <li>Reactive</li>
      </ul>
    </ul>
    <p>Count: {count}</p>
    <button class="mt-4" on:click={incrementCount}>Increment</button>
    <label class="block mt-4">Your name: <input type="text" bind:value={name} /></label>
    <div>My fancy name: {myFancyName}</div>
    <Users title="My lovely users" bind:myName={name} />
  </div>
</main>
arstarst arstarstarstarstarstarstarstarstartarstarstarstarstarstarstarstarstarstarstarstarsta

<style lang="postcss">
  :root {
    font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Oxygen, Ubuntu, Cantarell, 'Open Sans',
      'Helvetica Neue', sans-serif;
  }

  img {
    height: 16rem;
    width: 16rem;
  }

  ul {
    list-style: initial;
    padding-left: 2em;
  }
  arst button {
    @apply border px-4 py2 bg-indigo-500 text-white rounded-xl;
  }
</style>

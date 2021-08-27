<script lang="ts">
  import logo from './assets/svelte.png'
  import './Tailwind.svelte'
</script>

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
</style>

<main>
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
</main>

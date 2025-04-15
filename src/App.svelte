<script lang="ts">
  import svelteLogo from './assets/svelte.svg'
  import viteLogo from '/vite.svg'
  import Counter from './lib/Counter.svelte'

  import "carbon-components-svelte/css/all.css";
  //let theme = "white"; // "white" | "g10" | "g80" | "g90" | "g100"
  let theme = "g90";
  $: document.documentElement.setAttribute("theme", theme);

  import { Button, breakpoints } from "carbon-components-svelte";

  import {
    Theme,
    RadioButtonGroup,
    RadioButton,
  } from "carbon-components-svelte";
</script>

<main>
  <div>
    <a href="https://vite.dev" target="_blank" rel="noreferrer">
      <img src={viteLogo} class="logo" alt="Vite Logo" />
    </a>
    <a href="https://svelte.dev" target="_blank" rel="noreferrer">
      <img src={svelteLogo} class="logo svelte" alt="Svelte Logo" />
    </a>
  </div>
  <h1>Vite + Svelte</h1>

  <div class="card">
    <Counter />
  </div>

  <p>
    Check out <a href="https://github.com/sveltejs/kit#readme" target="_blank" rel="noreferrer">SvelteKit</a>, the official Svelte app framework powered by Vite!
  </p>

  <p class="read-the-docs">
    Click on the Vite and Svelte logos to learn more
  </p>

  <Theme bind:theme persist persistKey="__carbon-theme" />

  <RadioButtonGroup legendText="Carbon theme" bind:selected={theme}>
    {#each ["white", "g10", "g80", "g90", "g100"] as value}
      <RadioButton labelText={value} {value} />
    {/each}
  </RadioButtonGroup>
</main>

<style>
  .logo {
    height: 6em;
    padding: 1.5em;
    will-change: filter;
    transition: filter 300ms;
  }
  .logo:hover {
    filter: drop-shadow(0 0 2em #646cffaa);
  }
  .logo.svelte:hover {
    filter: drop-shadow(0 0 2em #ff3e00aa);
  }
  .read-the-docs {
    color: #888;
  }
</style>

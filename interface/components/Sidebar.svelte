<script>
  import { view } from "../stores.js"

  let isExpanded = false

  const mouseover = () => {
    isExpanded = true
  }

  const handleView = () => {
    $view.current = $view.view
  }
  const handleCreate = () => {
    $view.current = $view.create
  }
  const handleVote = () => {
    $view.current = $view.vote
  }
  const handleHome = () => {
    $view.current = $view.home
  }
</script>

<!-- svelte-ignore a11y-mouse-events-have-key-events -->
<nav class:expanded={isExpanded} on:mouseover={() => mouseover()}>
  <ul>
    {#if isExpanded}
      <!-- svelte-ignore a11y-click-events-have-key-events -->
      <li on:click={() => handleHome()}>  Home 🏠</li>
      <!-- svelte-ignore a11y-click-events-have-key-events -->
      <li on:click={() => handleView()}>  View 🚀</li>
      <!-- svelte-ignore a11y-click-events-have-key-events -->
      <li on:click={() => handleCreate()}>  Create ⭐️</li>
      <!-- svelte-ignore a11y-click-events-have-key-events -->
      <li on:click={() => handleVote()}>  Vote 🗑</li>
    {/if}
  </ul>
</nav>

<style>
  nav {
    min-height: 100vh;
    background-color: #010101;
    color: #a2b7c4;
    transition: ease-out 200ms;
    width: 12vmin;
    position: relative;
  }

  .expanded {
    transition: ease-out 200ms;
    min-height: 100vh;
    background-color: rgb(14, 13, 13);
    color: #ffffff;
    transition: ease-out 200ms;
    width: 16vmin;
  }

  ul {
    list-style: none;
    padding-left: 1vmin;
    padding-right: 1vmin;
    margin: 0;
    margin-top: 2vmin;
  }

  li {
    width: 100%;
    padding-top: 2vmin;
    padding-bottom: 2vmin;
    display: flex;
    flex-direction: column;
    justify-content: center;
    font-weight: 600;
    font-size: 1em;
    cursor: pointer;
  }

  li:hover {
    background-color: #407896;
    transition: 300ms;
    transform: scale(1.08);
  }
</style>

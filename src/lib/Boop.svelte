<script>
  import { fade, scale } from 'svelte/transition';
  let counter = 0;
  $: derivedCount = 10 - counter;

  let state = 'NOT_BOOPED_ENOUGH';

  function increment() {
    counter++;
  }
</script>

<section>
  <p>{counter}</p>
  <button on:click={increment}>BOOP!</button>

  <p class="details">
  {#if state === 'MOAR_BOOPS'}
    <span transition:fade={{ delay: 400 }}>WE ARE AT MAXIMUM BOOPERDRIVE!</span>
  {/if}

  {#if derivedCount > 0}
    <span
      transition:scale
      on:outroend="{() => state = 'MOAR_BOOPS'}"
    >
      We are {derivedCount} boops away from MAXIMUM BOOPERDRIVE!
    </span>
  {/if}
  </p>
</section>

<style>
  section {
    display: flex;
    flex-direction: column;
    align-items: center;
  }

  p {
    font-size: 2rem;
    margin-bottom: 0.5rem;
  }

  span {
    display: block;
  }

  button {
    background: var(--accent-color);
    border: none;
    color: var(--pure-white);
    font-size: 1.25rem;
    font-weight: bold;
    padding: 0.5rem 1.5rem;
  }

  .details {
    font-size: 1.25rem;
  }
</style>
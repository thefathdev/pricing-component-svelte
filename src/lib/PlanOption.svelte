<script>
  import data from '../data.json'
  import Card from './components/Card.svelte'
  export let plan = 'annually'
</script>

<div class="plan-option">
  {#each data as detail}
    <Card {detail} {plan} />
  {/each}
</div>

<style>
  .plan-option {
    display: flex;
    flex-direction: column;
    gap: 2.25em;
  }
</style>

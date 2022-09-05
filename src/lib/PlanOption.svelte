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
    max-width: 32rem;
    margin: 0 auto;
  }

  @media (min-width: 48rem) {
    .plan-option {
      display: grid;
      grid-template-columns: repeat(3, 1fr);
      gap: 0;
      margin: 0;
      max-width: 65rem;
      margin: 0 auto;
      align-items: center;
    }
  }
</style>

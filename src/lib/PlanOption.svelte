<script>
  import data from '../data.json'
  import Card from './components/Card.svelte'
  export let plan = 'annually'
</script>

<h2>{plan}</h2>
<div class="plan-option">
  {#each data as detail}
    <Card {detail} {plan} />
  {/each}
</div>

<script>
  import Header from './lib/Header.svelte'
  import ChoosePlan from './lib/ChoosePlan.svelte'
  import PlanOption from './lib/PlanOption.svelte'
  import Background from './lib/components/Background.svelte'

  let plan = 'annually'

  const changePlan = (e) => {
    plan = e.detail ? 'monthly' : 'annually'
    console.log(plan)
  }
</script>

<main class="container">
  <Background />
  <div class="wrapper">
    <Header marginBottom="1em" />
    <ChoosePlan on:changePlan={changePlan} marginBottom="0.5em" />
    <PlanOption {plan} />
  </div>
</main>

<style>
  .container {
    background-color: var(--clr-neutral-100);
    min-height: 100vh;
    min-width: 100vw;
    position: relative;
    z-index: 1;
  }
  .wrapper {
    display: flex;
    flex-direction: column;
    align-items: center;
    position: relative;
    z-index: 3;
    padding: 4em 1em;
  }
</style>

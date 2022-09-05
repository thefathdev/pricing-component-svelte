<!-- Toggle -->
<script>
  import { createEventDispatcher } from 'svelte'

  export let marginBottom = '0.5em'

  let dispatch = createEventDispatcher()

  let checked = false

  const handleChange = () => {
    dispatch('changePlan', checked)
  }
</script>

<div class="choose-plan" style="margin-bottom: {marginBottom};">
  <p class="plan-timeframe">Annually</p>
  <label class="switch">
    <input type="checkbox" bind:checked on:change={handleChange} />
    <span class="slider" />
  </label>
  <p class="plan-timeframe">Monthly</p>
</div>

<style>
  .choose-plan {
    display: flex;
    align-items: center;
    justify-content: center;
    gap: 1.25em;
  }

  .plan-timeframe {
    color: var(--clr-neutral-200);
  }

  .switch {
    position: relative;
    display: inline-block;
    width: 4rem;
    height: 2rem;
    transition: opacity 300ms ease-in-out;
  }

  .switch:hover,
  .switch:focus {
    opacity: 0.75;
  }

  .switch input {
    opacity: 0;
    width: 0;
    height: 0;
  }

  .slider {
    position: absolute;
    cursor: pointer;
    top: 0;
    left: 0;
    right: 0;
    bottom: 0;
    background: linear-gradient(
      300deg,
      var(--clr-primary-2) 20%,
      var(--clr-primary-1) 80%
    );
    -webkit-transition: 0.4s;
    transition: 0.4s;
    border-radius: 2rem;
  }

  .slider:before {
    position: absolute;
    content: '';
    height: 1.5rem;
    width: 1.5rem;
    left: 0.25rem;
    bottom: 0.25rem;
    background-color: white;
    -webkit-transition: 0.4s;
    transition: 0.4s;
    border-radius: 50%;
  }

  input:checked + .slider:before {
    -webkit-transform: translateX(2rem);
    -ms-transform: translateX(2rem);
    transform: translateX(2rem);
  }
</style>

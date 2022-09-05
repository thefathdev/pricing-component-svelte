<script>
  import Button from './Button.svelte'
  export let detail = {}
  export let plan = ''

  let count = 0
</script>

<div class="card">
  <h2 class="plan-name">{detail.plan}</h2>
  <p class="plan-price">
    <small class="dollar-sign">$</small>{detail.price[plan]}
  </p>
  <ul class="plan-features">
    <li class="plan-item">{detail.features.storage} Storage</li>
    <li class="plan-item">{detail.features.users} Users Allowed</li>
    <li class="plan-item">Send up to {detail.features.send}</li>
  </ul>
  <Button
    btnBg="var(--card-btn-bg)"
    btnText="var(--card-btn-text)"
    btnBorder="var(--card-btn-border)">learn More</Button
  >
</div>

<style>
  /* Style the card */
  ul,
  li {
    list-style-type: none;
    margin: 0;
    padding: 0;
  }

  .card {
    --card-main-bg: var(--clr-neutral-0);
    --card-btn-bg: linear-gradient(
      300deg,
      var(--clr-primary-2) 20%,
      var(--clr-primary-1) 80%
    );
    --card-btn-text: var(--card-main-bg);
    --card-btn-border: var(--clr-primary-2);
    --card-text-clr-1: var(--clr-neutral-600);
    --card-text-clr-2: var(--clr-neutral-400);
    --card-line-clr: var(--clr-neutral-200);
    background: var(--card-main-bg);
    color: var(--card-text-clr-1);
    padding: 2em;
    border-radius: 8px;
    box-shadow: var(--bs-smooth);
    display: flex;
    flex-direction: column;
  }

  .card:nth-child(2) {
    --card-main-bg: linear-gradient(
      300deg,
      var(--clr-primary-2) 20%,
      var(--clr-primary-1) 80%
    );
    --card-btn-bg: var(--clr-neutral-0);
    --card-btn-text: var(--clr-primary-2);
    --card-text-clr-1: var(--clr-neutral-0);
    --card-text-clr-2: var(--clr-neutral-0);
    --card-line-clr: var(--clr-neutral-0);
    --card-btn-border: var(--clr-neutral-0);
  }

  .plan-name {
    margin-bottom: 0.4em;
    text-transform: capitalize;
    text-align: center;
    color: var(--card-text-clr-2);
    font-size: 1.2em;
  }

  .plan-price {
    margin-bottom: 0.3em;
    text-align: center;
    font-size: 4.2em;
    display: flex;
    justify-content: center;
    align-items: center;
    gap: 0.05em;
  }

  .plan-features {
    margin-bottom: 2em;
    display: flex;
    flex-direction: column;
  }

  .plan-item {
    text-align: center;
    border-top: 1px solid var(--card-line-clr);
    padding: 1em 0;
    color: var(--card-text-clr-2);
  }

  .plan-item:last-child {
    border-bottom: 1px solid var(--card-line-clr);
  }

  .dollar-sign {
    font-size: 0.6em;
  }

  @media (min-width: 48rem) {
    .card:nth-child(2) {
      padding: 3.5em 2em;
    }

    .card:first-child {
      border-radius: 8px 0 0 8px;
    }
    .card:last-child {
      border-radius: 0 8px 8px 0;
    }
  }
</style>

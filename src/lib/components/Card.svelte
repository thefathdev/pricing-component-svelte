<script>
  export let detail = {}
  export let plan = ''
</script>

<div class="card">
  <h2 class="plan-name">{detail.plan}</h2>
  <p>{detail.price[plan]}</p>
  <ul class="plan-features">
    <li class="plan-item">{detail.features.storage} Storage</li>
    <li class="plan-item">{detail.features.users} Users Allowed</li>
    <li class="plan-item">Send up to {detail.features.send}</li>
  </ul>
</div>

<style>
  /* Style the card */
</style>

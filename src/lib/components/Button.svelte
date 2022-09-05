<script>
  export let btnBg = 'black'
  export let btnText = 'white'
  export let btnBorder = 'black'
</script>

<button
  style="--clr-bg: {btnBg}; --clr-text: {btnText}; --clr-border: {btnBorder}"
  ><slot /></button
>

<style>
  button {
    cursor: pointer;
    background: var(--clr-bg);
    text-transform: uppercase;
    border: none;
    border-radius: 8px;
    padding: 1em;
    font-size: 0.9em;
    letter-spacing: 0.1em;
    color: var(--clr-text);
    outline-width: 0;
    transition: outline 500ms ease-in-out;
  }

  button:hover {
    outline: 1px solid var(--clr-border);
    background: none;
    color: var(--clr-border);
  }
</style>

<script>
  export let type = "primary";
  export let flat = false;
  export let inverse = false;
</script>

<button class={type} class:flat class:inverse>
  <slot />
</button>

<style>
  button {
    border: 0;
    cursor: pointer;
    border-radius: 6px;
    padding: 8px 12px;
    font-weight: bold;
    box-shadow: 1px 2px 3px rgba(0, 0, 0, 0.2);
  }

  .primary {
    background: #f93c6b;
    color: white;
  }

  .secondary {
    background: #5ad2f9;
    color: white;
  }

  .flat {
    box-shadow: none;
  }

  .primary.inverse {
    color: #f93c6b;
    background: white;
    border: 2px solid #f93c6b;
  }

  .secondary.inverse {
    color: #5ad2f9;
    background: white;
    border: 2px solid #5ad2f9;
  }
</style>

<script>
  export let data;
</script>

<slot />

<style>
  :global(body) {
    margin: 0;
    background-color: #000;
    color: #fff;
    font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
  }
  :root {
    --accent: rgb(100, 85, 65);
  }
</style>
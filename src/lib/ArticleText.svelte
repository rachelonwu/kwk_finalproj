<script>
  let { children } = $props();
</script>

<div class="article-text">
  <p>
    {@render children()}
  </p>
</div>

<style>
  .article-text {
    font-family: Georgia;
    margin: 50vh auto;
    width: 50%;
    background-color: #0d3d37;
    color: white;
    border: solid #0d3d37 3px;
    border-radius: 20px;
    padding: 20px;
    box-shadow: 16px 16px white;
  }
</style>

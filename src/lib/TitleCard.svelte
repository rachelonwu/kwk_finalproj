<script>
  let { title, subtitle } = $props();
</script>

<div class="title-card">
  <div class="content">
    <h1>{title}</h1>
    <p>{subtitle}</p>
  </div>
</div>

<style>
  .title-card {
    font-family: Georgia;
    background-color: #188f70;
    height: 100vh;
    display: flex;
    justify-content: center;
    align-items: center;
    text-align: center;
    padding: 2rem;
    box-sizing: border-box;
    font-family: "Inter", sans-serif;
  }

  .content {
    font-family: Georgia;
    max-width: 700px;
    background-color: #0d3d37;
    padding: 2rem;
    border: 6px solid #0d3d37;
    border-radius: 2rem;
    box-shadow: 16px 16px white;
  }

  h1 {
    font-family: Georgia;
    font-size: 3rem;
    margin: 0;
    color: white;
    text-shadow: 1px 1px 0 #007052;
  }

  p {
    font-family: Georgia;
    font-size: 1.3rem;
    color: #f7f5eb;
    margin-top: 1rem;
  }

  @media (max-width: 600px) {
    h1 {
      font-family: Georgia;
      font-size: 2.2rem;
    }

    p {
      font-family: Georgia;
      font-size: 1.1rem;
    }
  }
</style>

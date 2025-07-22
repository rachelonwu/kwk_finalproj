<script>
  import Scroller from "../lib/Scroller.svelte";
  import ArticleText from "../lib/ArticleText.svelte";
  import USMap from "../assets/us.png";
  import NCMap from "../assets/nc.png";
</script>

<div>
  <Scroller layout="left">
    {#snippet sticky()}
      <img src={USMap} alt="Map of the United States" />
    {/snippet}

    {#snippet scrolly()}
      <ArticleText
        >Here is the United States of America. Let's take a closer look at North
        Carolina.</ArticleText
      >
    {/snippet}
  </Scroller>
</div>

<div>
  <Scroller layout="left">
    {#snippet sticky()}
      <img src={NCMap} alt="Map of North Carolina" />
    {/snippet}

    {#snippet scrolly()}
      <ArticleText>There, that's more like it.</ArticleText>
    {/snippet}
  </Scroller>
</div>

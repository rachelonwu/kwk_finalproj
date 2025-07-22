<script>
  import * as Highcharts from "highcharts";
  import "highcharts/modules/exporting";
  import { Chart } from "@highcharts/svelte";
  import Scroller from "../lib/Scroller.svelte";
  import ArticleText from "../lib/ArticleText.svelte";
</script>

<div>
  <Scroller layout="left">
    {#snippet sticky()}{/snippet}

    {#snippet scrolly()}
      <ArticleText>[filler]</ArticleText>

      <ArticleText>[filler]</ArticleText>
    {/snippet}
  </Scroller>
</div>

<style>
</style>

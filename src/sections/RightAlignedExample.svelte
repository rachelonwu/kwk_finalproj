<script>
  import * as Highcharts from "highcharts";
  import "highcharts/modules/exporting";
  import { Chart } from "@highcharts/svelte";
  import Scroller from "../lib/Scroller.svelte";
  import ArticleText from "../lib/ArticleText.svelte";
  import MedianImg from "../assets/median.png";
</script>

<div>
  <Scroller layout="right">
    {#snippet sticky()}
      <img src={MedianImg} alt="Chart of Black Median Income" />
    {/snippet}

    {#snippet scrolly()}
      <ArticleText>
        To the right is a sample of North Carolina counties, displaying how
        their Black population's median income compares to the county's overall
        median income.
      </ArticleText>

      <ArticleText>
        There is quite a stark contrast between the 2 incomes. The Black median
        is notably <strong>lower</strong> than that of the state's.
      </ArticleText>

      <ArticleText>
        Why may this be the case? Let's take a closer look at how education
        plays a factor in Black wealth.
      </ArticleText>
    {/snippet}
  </Scroller>
</div>

<style>
</style>

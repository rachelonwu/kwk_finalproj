<script>
  import Scroller from "../lib/Scroller.svelte";
  import ObservedArticleText from "../lib/ObservedArticleText.svelte";

  // this `options` object below is passed into the <ObservedArticleText>
  // component, and from there it gets passed to the IntersectionObserver object w
  // when it's created.
  // the thresholds to fire the callback are 85% and 95%. in the callback function,
  // we check whether the visible area is >= 90%. so, triggering the callback at
  // 85% and 95% ensures we trigger the correct change in background color
  // whether the element is being scrolled into the viewport or out of the viewport.
  const options = {
    threshold: [0.85, 0.95],
  };

  const callback = (entries, observer) => {
    entries.forEach((entry) => {
      const elem = entry.target;

      if (entry.intersectionRatio >= 0.9) {
        // "active" state
        elem.style.backgroundColor = "#0d3d37";
      } else if (entry.intersectionRatio < 0.9) {
        // "inactive" state
        elem.style.backgroundColor = "#888888";
      }
    });
  };
</script>

<div>
  <Scroller layout="right">
    {#snippet sticky()}
      <div>
        <p>Here are the sources used to produce this website:</p>
      </div>
    {/snippet}

    {#snippet scrolly()}
      <ObservedArticleText {callback} {options}>
        [1] “Black Family Thriving | Urban Institute.” Www.urban.org, 11 Mar.
        2024, www.urban.org/research/publication/black-family-thriving.
      </ObservedArticleText>
    {/snippet}
  </Scroller>
</div>

<style>
  p {
    font-family: Georgia;
  }
</style>

<script>
  import { fade, fly } from "svelte/transition";
  import Scroller from "../lib/Scroller.svelte";
  import ObservedArticleText from "../lib/ObservedArticleText.svelte";
  import EducationImg from "../assets/education.png";
  let duckIsVisible = $state(false);

  const options = {
    threshold: [0.85, 0.95],
  };

  const simpleCallback = (entries, observer) => {
    entries.forEach((entry) => {
      const elem = entry.target;

      if (entry.intersectionRatio >= 0.9) {
        // "active" state
        elem.style.backgroundColor = "#e3ff00";
      } else if (entry.intersectionRatio < 0.9) {
        // "inactive" state
        elem.style.backgroundColor = "#888888";
      }
    });
  };

  const showDuckCallback = (entries, observer) => {
    entries.forEach((entry) => {
      const elem = entry.target;

      if (entry.intersectionRatio >= 0.9) {
        elem.style.backgroundColor = "#0d3d37";
        duckIsVisible = true;
      } else if (entry.intersectionRatio < 0.9) {
        elem.style.backgroundColor = "#888888";
      }
    });
  };

  const removeDuckCallback = (entries, observer) => {
    entries.forEach((entry) => {
      const elem = entry.target;

      if (entry.intersectionRatio >= 0.9) {
        elem.style.backgroundColor = "#0d3d37";
        duckIsVisible = false;
      } else if (entry.intersectionRatio < 0.9) {
        elem.style.backgroundColor = "#888888";
      }
    });
  };
</script>

<div>
  <Scroller layout="left">
    {#snippet sticky()}
      <div>
        {#if duckIsVisible}
          <img
            class="eduimg"
            src={EducationImg}
            alt="Higher Education Distribution for black People across NC"
            in:fly={{ y: 200, duration: 1000 }}
            out:fade
          />
        {/if}
        <br />
      </div>
    {/snippet}

    {#snippet scrolly()}
      <ObservedArticleText callback={removeDuckCallback} {options}>
        In a 2024 study, Charlotte, North Carolina was recognized as one of the
        metropolitan areas with various histories of Black in- and
        out-migration. The area expereinced an immense in-migration of the Black
        middle class.
      </ObservedArticleText>

      <ObservedArticleText callback={showDuckCallback} {options}>
        According to the American Community Service US Census of 2023, 20.6% of
        the North Carolina population is Black, and and only 24.6% of them have
        attained a Bachelor’s Degree or higher.
      </ObservedArticleText>

      <ObservedArticleText callback={removeDuckCallback} {options}>
        Higher education can serve as a marker of middle-class status,
        differentiating between white- and blue-collar jobs. [1]
      </ObservedArticleText>
    {/snippet}
  </Scroller>
</div>

<style>
  .eduimg {
    width: 700px;
    max-height: auto;
  }
</style>

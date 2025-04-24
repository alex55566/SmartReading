<template>
  <section class="about-wrapper">
    <h3>Why Ivi Green?</h3>
    <ul class="about-wrapper__points">
      <li v-for="point in points" key="point.id">
        <h4>{{ point.title }}</h4>
        <p>{{ point.text }}</p>
      </li>
    </ul>
    <div class="about-wrapper__sides">
      <div class="about-wrapper__side">
        <h5>The challenges teachers are facing</h5>
        <p>
          Teachers often face the challenge of spending extensive time searching
          for quality materials for their classes while students frequently
          approach them with more and more questions about their emotions,
          conflicts, self-organization methods, and family or friend
          relationships. The pandemic has exacerbated social-emotional problems
          among kids, making SEL one of the priorities for the school
          curriculum. Now even teachers specializing in subjects like math
          or language art need to incorporate social-emotional basics into their
          instructions.
        </p>
      </div>
      <div class="about-wrapper__side">
        <h5>Our solution</h5>
        <p>
          Our toolkits provide teachers with practical, visual, science-based
          resources to effectively teach social and emotional learning to teens.
          Designed to enhance emotional intelligence and build resilience, Ivi
          Green educational toolkits offer structured activities, comprehensive
          guidelines, and ready-to-use materials that cater to the unique
          developmental needs of adolescents. Educators can foster a supportive
          learning environment that promotes emotional well-being and academic
          success by integrating these tools into their teaching.
        </p>
      </div>
    </div>
    <Button text="Show all kits"></Button>
  </section>
</template>

<script setup lang="ts">
import Button from "@/ui/Button.vue";
import { nanoid } from "nanoid";
import { ref } from "vue";
const points = ref([
  {
    title: "40 000+",
    text: "products sold all around the world",
    id: nanoid(),
  },
  {
    title: "1 000+",
    text: "teachers use Ivi Green products",
    id: nanoid(),
  },
  {
    title: "30+",
    text: "countries use our toolkits to effectively teach ",
    id: nanoid(),
  },
]);
</script>

<style lang="scss" scoped>
.about-wrapper {
  @include FlexColumnCenterCenter;
  gap: getRem(35);
  h3 {
    font-weight: 700;
    font-size: getRem(40);
    color: $colorMineShaft;
  }
  &__points {
    @include FlexRowSpaceBetweenCenter;
    gap: getRem(30);
    width: 100%;
    li {
      @include FlexColumnCenterCenter;
      gap: getRem(10);
      h4 {
        font-size: getRem(64);
        font-weight: 700;
        color: $colorShamRock;
      }
      p {
        font-size: getRem(20);
        font-weight: 500;
        color: $colorMineShaft;
        text-align: center;
        max-width: getRem(285);
      }
    }
  }
  &__sides {
    @include FlexRowSpaceBetweenStretch;
    gap: getRem(30);
    .about-wrapper__side {
      @include FlexColumn;
      gap: getRem(20);
      padding: getRem(40);
      background-color: $colorAthensGray;
      border-radius: getRem(20);
      h5 {
        font-size: getRem(28);
        font-weight: 500;
        color: $colorChambray;
      }
      p {
        font-size: getRem(16);
        font-weight: 400;
        line-height: 140%;
        color: $colorMineShaft;
      }
    }
  }
}
</style>

<template>
  <section class="topics-wrapper">
    <h3>The most in-demand topics</h3>
    <ul class="topics-wrapper__list">
      <li class="topics-wrapper__item" v-for="topic in topics">
        <img :src="topic.img" alt="topic-pic" />
        <div>{{ topic.text }}</div>
      </li>
    </ul>
  </section>
</template>

<script setup lang="ts">
import demand1 from "@/assets/image/demand-1.svg";
import demand2 from "@/assets/image/demand-2.svg";
import demand3 from "@/assets/image/demand-3.svg";
import demand4 from "@/assets/image/demand-4.svg";
import demand5 from "@/assets/image/demand-5.svg";
import { nanoid } from "nanoid";
import { ref } from "vue";
const topics = ref([
  {
    img: demand1,
    id: nanoid(),
    text: "Relationships",
  },
  {
    img: demand2,
    id: nanoid(),
    text: "Skills development",
  },
  {
    img: demand3,
    id: nanoid(),
    text: "Growth mindset",
  },
  {
    img: demand4,
    id: nanoid(),
    text: "Emotional intelligence",
  },
  {
    img: demand5,
    id: nanoid(),
    text: "Self-esteem and confidence",
  },
]);
</script>

<style lang="scss" scoped>
.topics-wrapper {
  @include FlexColumnCenterCenter;
  gap: getRem(30);
  h3 {
    font-weight: 700;
    font-size: getRem(40);
    text-transform: uppercase;
  }
  .topics-wrapper__list {
    @include FlexRowCenterCenter;
    gap: getRem(20);
    flex-wrap: wrap;
    .topics-wrapper__item {
      display: flex;
      align-items: center;
      border: getRem(1) solid $colorChambray;
      color: $colorChambray;
      border-radius: getRem(100);
      font-size: getRem(28);
      font-weight: 500;
      img {
        width: getRem(90);
        height: getRem(90);
      }
      div {
        padding: getRem(25);
      }
    }
  }
}
</style>

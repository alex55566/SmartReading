<template>
  <section class="hero-wrapper">
    <div class="hero-wrapper__left">
      <h3>Social-Emotional Learning Toolkits and Soft Skills for Educators</h3>
      <p>
        Fostering emotional intelligence and progressive mindset in teen
        students
      </p>
      <Button text="Show all kits"></Button>
    </div>
    <div class="hero-wrapper__right">
      <img src="@/assets/image/hero-img.svg" alt="hero-pic" />
      <p class="first">Engaging activities for classroom and home use</p>
      <p class="second">Comprehensive guidelines for educators</p>
      <p class="third">Ready-to-use materials for SEL classes</p>
    </div>
  </section>
</template>

<script setup lang="ts">
import Button from "@/ui/Button.vue";
</script>

<style lang="scss" scoped>
.hero-wrapper {
  @include FlexRowSpaceBetweenCenter;
  gap: getRem(90);
  padding: getRem(35) 0;
  &__left {
    @include FlexColumn;
    gap: getRem(30);
    max-width: getRem(520);
    color: $colorWhite;
    h3 {
      font-size: getRem(40);
      font-weight: 700;
      text-transform: uppercase;
    }
    p {
      font-size: getRem(28);
      font-weight: 500;
    }
  }
  &__right {
    position: relative;
    width: getRem(600);
    height: getRem(600);
    img {
      width: 100%;
      height: auto;
    }
    p {
      position: absolute;
      max-width: getRem(180);
      font-size: getRem(16);
      font-weight: 500;
      color: $colorMineShaft;
      text-align: center;
    }
    .first {
      top: getRem(67);
      left: getRem(10);
    }
    .second {
      top: 50%;
      right: getRem(10);
      transform: translateY(-50%);
    }
    .third {
      bottom: getRem(67);
      left: 50%;
      transform: translateX(-50%);
    }
  }
}
</style>

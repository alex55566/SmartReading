<template>
  <header class="header-wrapper">
    <a class="header-wrapper__logo" href="/"
      ><img src="@/assets/image/logo.svg" alt="logo-pic"
    /></a>
    <ul class="header-wrapper__links">
      <li v-for="link in links" key="link.id">
        <a :href="link.url">{{ link.name }}</a>
      </li>
    </ul>
    <a class="header-wrapper__basket" href="/#basket">
      <img src="@/assets/image/basket.svg" alt="basket-pic" />
      <span>3</span>
    </a>
  </header>
</template>

<script setup lang="ts">
import { nanoid } from "nanoid";
import { ref } from "vue";
const links = ref([
  {
    name: "Products",
    url: "/#products",
    id: nanoid(),
  },
  {
    name: "About Ivi Green",
    url: "/#about",
    id: nanoid(),
  },
  {
    name: "FAQ",
    url: "/#faq",
    id: nanoid(),
  },
  {
    name: "For educators",
    url: "/#educators",
    id: nanoid(),
  },
  {
    name: "Blog",
    url: "/#blog",
    id: nanoid(),
  },
]);
</script>

<style lang="scss" scoped>
.header-wrapper {
  @include FlexRowSpaceBetweenCenter;
  padding: getRem(16);
  gap: getRem(80);
  &__logo {
    width: getRem(80);
    height: getRem(80);
    img {
      width: 100%;
      height: auto;
    }
  }
  &__links {
    @include FlexRowSpaceBetweenCenter;
    gap: getRem(80);
    font-size: getRem(20);
    font-weight: 500;
    color: $colorMineShaft;
  }
  &__basket {
    position: relative;
    width: getRem(27);
    height: getRem(27);
    img {
      width: 100%;
      height: auto;
    }
    span {
      position: absolute;
      top: getRem(-9);
      right: getRem(-9);
      @include FlexRowCenterCenter;
      width: getRem(25);
      height: getRem(25);
      border-radius: 50%;
      background-color: $colorShamRock;
      color: $colorWhite;
      font-size: getRem(16);
      font-weight: 500;
    }
  }
}
</style>

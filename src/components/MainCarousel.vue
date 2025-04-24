<template>
  <section class="slider-container">
    <swiper
      :slides-per-view="1"
      :space-between="0"
      :modules="modules"
      :scrollbar="{ draggable: true }"
      :navigation="{
        nextEl: '.swiper-button-next',
        prevEl: '.swiper-button-prev',
      }"
      class="main-swiper"
    >
      <swiper-slide v-for="slide in slides" :key="slide.id" class="slide">
        <img :src="slide.img" alt="carousel-pic" />
      </swiper-slide>
    </swiper>

    <button class="swiper-button-prev"></button>
    <button class="swiper-button-next"></button>
  </section>
</template>

<script setup lang="ts">
import carousel1 from "@/assets/image/carousel-1.png";
import { nanoid } from "nanoid";
import "swiper/css"; // Основные стили Swiper
import "swiper/css/navigation"; // Стили навигации
import { A11y, Navigation, Scrollbar } from "swiper/modules";
import { Swiper, SwiperSlide } from "swiper/vue";
import { ref } from "vue";
const modules = [Scrollbar, A11y, Navigation];
const slides = ref([
  {
    img: carousel1,
    id: nanoid(),
  },
  {
    img: carousel1,
    id: nanoid(),
  },
  {
    img: carousel1,
    id: nanoid(),
  },
]);
</script>

<style lang="scss" scoped>
.slider-container {
  position: relative;
  width: getRem(992);
  margin: 0 auto;
}

.swiper {
  width: 100%;
  height: getRem(500);
  border-radius: getRem(20);
}

.swiper-slide {
  display: flex;
  justify-content: center;
  align-items: center;

  img {
    width: 100%;
    height: 100%;
    object-fit: cover;
    border-radius: getRem(20);
  }
}

.swiper-button-prev,
.swiper-button-next {
  position: absolute;
  top: 50%;
  transform: translateY(-50%);
  width: getRem(80);
  height: getRem(80);
  background: $colorShamRock;
  border-radius: 50%;
  z-index: 10;
  cursor: pointer;
  display: flex;
  align-items: center;
  justify-content: center;
  &::after {
    content: "";
    width: getRem(20);
    height: getRem(20);
    background-image: url("@/assets/image/carousel-arrow.svg");
    background-size: contain;
    background-repeat: no-repeat;
  }
}

.swiper-button-prev {
  left: getRem(-100);
}

.swiper-button-next {
  right: getRem(-100);
  &::after {
    transform: rotate(180deg);
  }
}
</style>

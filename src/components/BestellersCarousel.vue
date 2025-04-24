<template>
  <section class="slider-container">
    <h3>Our Bestsellers</h3>
    <swiper
      :slides-per-view="2"
      :space-between="25"
      :modules="modules"
      :scrollbar="{ draggable: true }"
      :navigation="{
        nextEl: '.swiper-button-next',
        prevEl: '.swiper-button-prev',
      }"
      class="main-swiper"
    >
      <swiper-slide v-for="slide in slides" :key="slide.id" class="slide">
        <div class="slide-wrapper">
          <img :src="slide.img" alt="carousel-pic" />
          <div class="slide-content">
            <div class="slide-wrapper__price">
              <div class="new-price">$19.99</div>
              <div class="old-price">$39.99</div>
              <div class="discount">50% off</div>
            </div>
            <h3 class="slide-wrapper__title">{{ slide.title }}</h3>
            <p class="slide-wrapper__text">{{ slide.text }}</p>
          </div>
          <Button text="Add to cart"></Button>
        </div>
      </swiper-slide>
    </swiper>
    <button class="swiper-button-prev"></button>
    <button class="swiper-button-next"></button>
    <a class="slider-container__link" href="/more">
      <span>Show all</span>
      <img src="@/assets/image/arrow-right.svg" alt="arrow-right" />
    </a>
  </section>
</template>

<script setup lang="ts">
import bestellers1 from "@/assets/image/bestellers-1.png";
import bestellers2 from "@/assets/image/bestellers-2.png";
import Button from "@/ui/Button.vue";
import { nanoid } from "nanoid";
import "swiper/css"; // Основные стили Swiper
import "swiper/css/navigation"; // Стили навигации
import { A11y, Navigation, Scrollbar } from "swiper/modules";
import { Swiper, SwiperSlide } from "swiper/vue";
import { ref } from "vue";
const modules = [Scrollbar, A11y, Navigation];
const slides = ref([
  {
    img: bestellers1,
    id: nanoid(),
    title: "RELATIONSHIPS FOR TEENS AND TWEENS",
    text: "Equip your teens with the necessary self-confidence, enabling them to cultivate healthy relationship habits for their happiness",
  },
  {
    img: bestellers2,
    id: nanoid(),
    title: "EMOTIONS FOR TEENS AND TWEENS",
    text: "Help your teens deal with anger, fear, and anxiety. Give them tools to manage their emotional self",
  },
  {
    img: bestellers1,
    id: nanoid(),
    title: "RELATIONSHIPS FOR TEENS AND TWEENS",
    text: "Equip your teens with the necessary self-confidence, enabling them to cultivate healthy relationship habits for their happiness",
  },
  {
    img: bestellers2,
    id: nanoid(),
    title: "RELATIONSHIPS FOR TEENS AND TWEENS",
    text: "Equip your teens with the necessary self-confidence, enabling them to cultivate healthy relationship habits for their happiness",
  },
]);
</script>

<style lang="scss" scoped>
.slider-container {
  margin: 0 auto;
  position: relative;
  padding: getRem(100) 0;
  width: getRem(950);
  h3 {
    margin-bottom: getRem(30);
    font-weight: 700;
    font-size: getRem(40);
    color: $colorWhite;
    text-align: center;
  }
}

.main-swiper {
  padding: 0 getRem(10);
  margin-bottom: getRem(30);
}

.swiper-slide {
  width: 100%;
  max-width: getRem(460);
  height: auto;
  background-color: $colorAlabaster;
  border-radius: getRem(20);
  padding: getRem(25);
  box-sizing: border-box;

  .slide-wrapper {
    @include FlexColumn;
    height: 100%;
    gap: getRem(30);
    position: relative;
    img {
      width: 100%;
      max-height: getRem(250);
      object-fit: contain;
    }
    h3 {
      font-weight: 500;
      font-size: getRem(28);
      color: $colorMineShaft;
    }
    p {
      font-weight: 500;
      font-size: getRem(20);
      color: $colorMineShaft;
    }
  }
}

.slide-wrapper__price {
  @include FlexRowStartCenter;
  gap: getRem(16);
  .new-price {
    font-size: getRem(28);
    font-weight: 500;
    color: $colorChambray;
  }
  .old-price {
    font-size: getRem(20);
    font-weight: 500;
    color: $colorMineShaft;
    text-decoration: line-through;
  }
  .discount {
    padding: getRem(5) getRem(10);
    font-size: getRem(20);
    font-weight: 700;
    color: $colorWhite;
    border-radius: getRem(8);
    background-color: $colorFlamingo;
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

.slide-content {
  @include FlexColumn;
  gap: getRem(20);
  flex: 1;
}

Button {
  margin-top: getRem(20);
  align-self: center;
  width: 100%;
}

.slider-container__link {
  font-size: getRem(20);
  font-weight: 700;
  @include FlexRowCenterCenter;
  gap: getRem(10);
  color: $colorWhite;
  text-align: center;
  img {
    width: getRem(24);
    height: getRem(24);
  }
}
</style>

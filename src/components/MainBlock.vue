<template>
  <main class="main-wrapper">
    <div class="wide-layout wide-layout__offset">
      <ContainerLayout>
        <MainHero />
      </ContainerLayout>
    </div>
    <ContainerLayout>
      <MainAbout />
    </ContainerLayout>
    <ContainerLayout>
      <MainCarousel />
    </ContainerLayout>
    <ContainerLayout>
      <MainTopics />
    </ContainerLayout>
    <div class="wide-layout">
      <ContainerLayout>
        <BestellersCarousel />
      </ContainerLayout>
    </div>
    <ContainerLayout>
      <MainForm />
    </ContainerLayout>
  </main>
</template>

<script setup lang="ts">
import BestellersCarousel from "@/components/BestellersCarousel.vue";
import ContainerLayout from "@/components/Layouts/ContainerLayout.vue";
import MainAbout from "@/components/MainAbout.vue";
import MainCarousel from "@/components/MainCarousel.vue";
import MainForm from "@/components/MainForm.vue";
import MainHero from "@/components/MainHero.vue";
import MainTopics from "@/components/MainTopics.vue";
</script>

<style lang="scss" scoped>
.main-wrapper {
  @include FlexColumnCenterCenter;
  gap: getRem(100);
  width: 100%;
}
</style>

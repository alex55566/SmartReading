<template>
  <div class="layout">
    <ContainerLayout>
      <MainHeader />
    </ContainerLayout>
    <MainBlock />
    <ContainerLayout>
      <MainFooter />
    </ContainerLayout>
  </div>
</template>

<script setup lang="ts">
import ContainerLayout from "@/components/Layouts/ContainerLayout.vue";
import MainBlock from "@/components/MainBlock.vue";
import MainFooter from "@/components/MainFooter.vue";
import MainHeader from "@/components/MainHeader.vue";
</script>

<style lang="scss"></style>

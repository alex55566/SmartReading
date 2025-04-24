<template>
  <div class="container-layout">
    <slot></slot>
  </div>
</template>

<script setup lang="ts"></script>

<style lang="scss">
.container-layout {
  width: getRem(1200);
}
</style>

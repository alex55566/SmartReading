<template>
  <button class="btn">{{ text }}</button>
</template>

<script setup lang="ts">
defineProps({
  text: String,
});
</script>

<style lang="scss" scoped>
button {
  padding: getRem(16);
  background-color: $colorShamRock;
  width: getRem(260);
  font-weight: 700;
  font-size: getRem(20);
  color: $colorWhite;
  border-radius: getRem(8);
}
</style>

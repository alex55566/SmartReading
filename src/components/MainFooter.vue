<template>
  <footer class="footer-wrapper">
    <a class="footer-wrapper__terms" href="/#term">Term of use </a>

    <a class="footer-wrapper__mail" href="mailto:hello@ivigreen.com">
      hello@ivigreen.com
    </a>
  </footer>
</template>

<script setup lang="ts"></script>

<style lang="scss" scoped>
.footer-wrapper {
  @include FlexRowSpaceBetweenCenter;
  padding: getRem(16);
  gap: getRem(80);
  a {
    font-size: getRem(20);
    font-weight: 500;
    color: $colorChambray;
    text-decoration: underline;
  }
}
</style>

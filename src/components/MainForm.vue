<template>
  <section class="form-wrapper">
    <form class="form-wrapper__form" action="">
      <h3>
        Drop your email to receive complimentary printables for your teens
      </h3>
      <div class="form-wrapper__input">
        <input type="email" placeholder="Enter your email" />
        <Button text="Get for free"></Button>
      </div>
      <p>
        By giving us your e-mail, you agree to our
        <a href="/#policy">privacy policy</a>
      </p>
    </form>
  </section>
</template>

<script setup lang="ts">
import Button from "@/ui/Button.vue";
</script>

<style lang="scss" scoped>
.form-wrapper {
  padding: getRem(60);
  border-radius: getRem(20);
  background-color: $colorChambray;
  color: $colorWhite;
  &__form {
    @include FlexColumnCenterCenter;
    gap: getRem(25);
  }
  h3 {
    font-weight: 500;
    font-size: getRem(28);
  }
  &__input {
    @include FlexRowNoneStretch;
    gap: getRem(25);
    input {
      padding: getRem(16);
      border-radius: getRem(8);
      border: none;
      width: getRem(460);
      font-size: getRem(20);
      &::placeholder {
        @include FlexRowCenterCenter;
        color: $colorMineShaft;
        font-size: getRem(20);
        opacity: 0.5;
      }
      &:focus {
        outline: none;
      }
    }
  }

  p {
    font-size: getRem(16);
    font-weight: 500;
    a {
      color: $colorShamRock;
    }
  }
}
</style>

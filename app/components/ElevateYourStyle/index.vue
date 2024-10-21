<template>
  <section class="elevate-your-style">
    <div class="elevate-your-style__container">
      <div class="elevate-your-style__body">
        <p class="elevate-your-style__body-text">
          Elevate Your Style <br/>
          Timeless Fashion, Sustainable <br/>
          Choices
        </p>
        <VButton>Shop Now</VButton>
      </div>
    </div>
  </section>
</template>

<style lang="scss">
.elevate-your-style {
  width: 100%;
  height: 712px;
  background-image: url('assets/img/elevateYourStyle/elevateYourStyleBgDesktop.png');
  background-size: cover;
  background-position: center center;
  padding-bottom: 64px;

  @media (max-width: $mobile) {
    height: 598px;
  }

  &__container {
    height: 100%;
    display: flex;
  }

  &__body {
    height: 100%;
    display: flex;
    flex-direction: column;
    justify-content: flex-end;
    align-items: start;
    gap: 20px;
    padding-left: 32px;
  }

  &__body-text {
    color: $color-white-1;
    font-size: 24px;
    line-height: 32px;
  }
}
</style>
<template>
  <section class="art-of-fewer">
    <div class="art-of-fewer__container">
      <div class="art-of-fewer__body">
        <h2 class="art-of-fewer__body-title">
          The Art of Fewer, Better Choices
        </h2>

        <p class="art-of-fewer__body-text">
          Opting for quality over quantity means selecting timeless, durable, and responsibly made items. This approach simplifies our lives and fosters a deeper appreciation for our surroundings. Emphasizing longevity and responsible production resonates with a more sustainable and mindful lifestyle.
        </p>
      </div>
    </div>
  </section>
</template>

<style lang="scss">
.art-of-fewer {
  padding: 96px 0 180px;
  background-color: $color-gray-1;

  &__body {
    display: flex;
    flex-direction: column;
    align-items: center;
    text-align: center;
    gap: 48px;

    &-title {
      font-size: 24px;

      @media (max-width: $mobileSmall) {
        width: 307px;
      }
    }

    &-text {
      max-width: 720px;

      @media (max-width: $mobileSmall) {
        width: 307px;
      }
    }

  }
}
</style>
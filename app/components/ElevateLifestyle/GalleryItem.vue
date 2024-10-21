<template>
  <section class="gallery-item">
    <div class="gallery-item__product">
      <img :src="props.src" :alt="props.description" class="gallery-item__product-image"/>
    </div>
    <h3 class="gallery-item__description">{{props.description}}</h3>
  </section>
</template>

<script lang="ts" setup>
interface Props {
  src: string;
  description: string;
}

const props = defineProps<Props>();
</script>

<style lang="scss">
.gallery-item {
  position: relative;

  &__product-image {
    width: 432px;
    height: 532px;
    object-fit: cover;

    @media (max-width: $tablet) {
      width: 343px;
      height: 343px;
    }
  }

  &__description {
    color: $color-white-1;
    font-size: 18px;
    position: absolute;
    left: 32px;
    bottom: 32px;
  }
}
</style>
<template>
  <section class="collection-banners">
    <div class="collection-banners__container">
      <div class="collection-banners__body">
        <div v-for="item in data" :key="item.description" class="collection-banners__body-item">
          <div class="collection-banners__product">
            <img :src="item.src" :alt="item.description" class="collection-banners__product-image"/>
          </div>
          <h3 class="collection-banners__description">{{item.description}}</h3>
        </div>
      </div>
    </div>
  </section>
</template>

<script lang="ts" setup>
const data = {
  theSmartChic: {
    src: '/img/collectionBanners/theSmartChic.png',
    description: 'The Smart Chic',
  },
  readyToGo: {
    src: '/img/collectionBanners/readyToGo.png',
    description: 'Ready To Go',
  }
}
</script>

<style lang="scss">
.collection-banners {
  padding: 32px 0;

  &__body {
    display: flex;
    gap: 20px;
    justify-content: space-between;

    @media (max-width: $tablet) {
      flex-direction: column;
    }
  }

  &__body-item {
    position: relative;
    flex: 1;
  }

  &__product-image {
    width: 100%;
    height: 719px;
    object-fit: cover;

    @media (max-width: $mobileSmall) {
      width: 100%;
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
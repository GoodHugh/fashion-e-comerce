<template>
  <section class="elevate-lifestyle">
    <div class="elevate-lifestyle__container">
      <div class="elevate-lifestyle__body">
        <h2 class="elevate-lifestyle__body-title">
          Elevate your lifestyle with a more intelligent, superior wardrobe. <br/>
          Our range is crafted sustainably with longevity in mind.
        </h2>

        <div class="elevate-lifestyle__body-gallery">
          <ElevateLifestyleGalleryItem
              v-for="item in galleryData"
              :key="item.description"
              :src="item.src"
              :description="item.description"
          />
        </div>
      </div>
    </div>
  </section>
</template>

<script setup lang="ts">
  const galleryData = {
    newArrivals: {
      src: '/img/elevateLifestyle/newArrivals.png',
      description: 'New Arrivals',
    },
    theCasualEdit: {
      src: '/img/elevateLifestyle/theCasualEdit.jpeg',
      description: 'The Casual Edit',
    },
    bestSellers: {
      src: '/img/elevateLifestyle/bestSellers.jpeg',
      description: 'Best Sellers'
    }
  }
</script>

<style lang="scss">
.elevate-lifestyle {

  &__body {
    display: flex;
    flex-direction: column;
    gap: 48px;
    padding: 32px 0;
  }

  &__body-title {
    padding: 16px;
    font-size: 18px;
  }

  &__body-gallery {
    display: flex;
    flex-wrap: wrap;
    align-items: center;
    gap: 20px;

    //@media (max-width: $mobile) {
    //  flex-direction: column;
    //}
  }
}
</style>
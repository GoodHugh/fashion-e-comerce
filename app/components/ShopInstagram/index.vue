<template>
  <section class="shop-instagram">
    <div class="shop-instagram__container">
      <div class="shop-instagram__body">
        <h2 class="shop-instagram__body-title">
          Shop Instagram
        </h2>

        <div class="shop-instagram__body-gallery">
          <NuxtLink v-for="img in data" :key="img.alt" class="shop-instagram__body-gallery-item" to="#"  target="_blank">
            <img class="shop-instagram__body-gallery-item-img" :src="img.src" :alt="img.alt" />
            <div class="shop-instagram__body-gallery-item-img-hover">
              <IconsInstagramLogo />
            </div>
          </NuxtLink>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup lang="ts">

const data = {
  inst1: {
    src: '/img/instagram/instagram-1.png',
    alt: 'inst1'
  },
  inst2: {
    src: '/img/instagram/instagram-2.png',
    alt: 'inst2'
  },
  inst3: {
    src: '/img/instagram/instagram-3.jpeg',
    alt: 'inst3'
  },
  inst4: {
    src: '/img/instagram/instagram-4.png',
    alt: 'inst4'
  },
  inst5: {
    src: '/img/instagram/instagram-5.png',
    alt: 'inst5'
  },
}

</script>

<style lang="scss">
.shop-instagram {
  padding: 32px 0;

  &__body {
    display: flex;
    flex-direction: column;
    gap: 48px;

    &-title {
      font-size: 24px;
      text-align: center;
      padding: 16px;
    }

    &-gallery {
      display: flex;
      justify-content: space-between;
      //gap: 20px;
    }

    &-gallery-item {
      position: relative;

      @media (max-width: $pc) {
        &:nth-child(4),
        &:nth-child(5) {
          display: none;
        }
      }
    }

    &-gallery-item-img {
      width: 251.2px;
      height: 251.2px;
      object-fit: cover;

      @media (max-width: $mobile) {
        width: 101px;
        height: 101px;
      }
    }

    &-gallery-item-img-hover {
      display: flex;
      align-items: center;
      justify-content: center;
      position: absolute;
      top: 0;
      bottom: 0;
      left: 0;
      right: 0;
      opacity: 0;
      background-color: rgba($color-black-1, 0.5);

      &:hover {
        opacity: 1;
        transition: all .4s ease;
      }
    }
  }
}
</style>
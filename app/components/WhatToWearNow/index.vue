<template>
  <section class="what-to-wear-now">
    <div class="what-to-wear-now__container">
      <div class="what-to-wear-now__body">
        <h2 class="what-to-wear-now__body-title">
          What to Wear Now
        </h2>

          <div class="what-to-wear-now__body-gallery">
            <WhatToWearNowGalleryItem
              v-for="(item, index) in data"
              :key="item.title"
              :src="item.src"
              :title="item.title"
              :price="item.price"
              :palette="item.palette"
              :isOpen="openIndex === index"
              @toggle="handleToggle(index)"
            />
          </div>
      </div>
    </div>
  </section>
</template>

<script lang="ts" setup>
const data = {
  classicEasyZipperTote: {
    src: '/img/whatToWearNow/classicEasyZipperTote.png',
    title: 'Classic Easy Zipper Tote',
    price: '$298',
    palette: [
      '#B8967B',
      '#000000',
      '#F5B4B4'
    ]
  },
  concertinaPhoneBag: {
    src: '/img/whatToWearNow/concertinaPhoneBag.png',
    title: 'Concertina Phone Bag',
    price: '$248',
    palette: [
      '#B8967B',
      '#000000',
      '#F5B4B4'
    ]
  },
  woolCashmereSweaterCoat: {
    src: '/img/whatToWearNow/woolCashmereSweaterCoat.png',
    title: 'Wool Cashmere Sweater Coat',
    price: '$398',
    palette: [
      '#B8967B',
      '#000000',
      '#F5B4B4'
    ]
  },
  singleOriginCashmereBeanie: {
    src: '/img/whatToWearNow/singleOriginCashmereBeanie.png',
    title: 'Single-Origin Cashmere Beanie',
    price: '$98',
    palette: [
      '#B8967B',
      '#000000',
      '#F5B4B4'
    ]
  },
  alpacaWoolCroppedCardigan: {
    src: '/img/whatToWearNow/alpacaWoolCroppedCardigan.png',
    title: 'Alpaca Wool Cropped Cardigan',
    price: '$248',
    palette: [
      '#B8967B',
      '#000000',
      '#F5B4B4'
    ]
  },
}

const openIndex = ref<number | null>(null)

const handleToggle = (index: number) => {
  if (openIndex.value === index) {
    openIndex.value = null
  } else {
    openIndex.value = index
  }
}
</script>

<style lang="scss">
.what-to-wear-now {
  padding: 32px 0;
  overflow: hidden;


  &__body {
    display: flex;
    flex-direction: column;
    gap: 48px;

    &-title {
      padding: 16px;
    }

    &-gallery {
      display: flex;
      gap: 20px;
      overflow-x: auto;
      scrollbar-width: none;
      -ms-overflow-style: none;

      &::-webkit-scrollbar {
        display: none;
      }
    }

  }
}
</style>
<template>
  <div class="what-to-wear-now-gallery-item">
    <div class="what-to-wear-now-gallery-item__product">
      <img class="what-to-wear-now-gallery-item__product-img" :src="props.src" :alt="props.title" />
      <button @click="toggleDropdown" class="what-to-wear-now-gallery-item__product-button">
        <IconsPlus />
      </button>
      <div class="what-to-wear-now-gallery-item__product-modal" :class="modalClassListModifiers">
        <p class="what-to-wear-now-gallery-item__product-modal-title">Data</p>
        <div class="what-to-wear-now-gallery-item__product-modal-theme">
          <div v-for="color in props.palette" class="what-to-wear-now-gallery-item__product-modal-theme-item">
            <div class="what-to-wear-now-gallery-item__product-modal-theme-item-color" :style="{ backgroundColor: color }"/>
          </div>
        </div>
      </div>
    </div>
    <div class="what-to-wear-now-gallery-item__info">
      <p class="what-to-wear-now-gallery-item__info-title">{{ props.title }}</p>
      <p class="what-to-wear-now-gallery-item__info-price">{{ props.price }}</p>
    </div>
  </div>
</template>

<script lang="ts" setup>
interface Props {
  src: string;
  title: string;
  price: string;
  palette: Array<string>;
  isOpen: boolean;
}

interface Emits {
  (event: 'toggle'): void;
}

const props = defineProps<Props>();
const emit = defineEmits<Emits>();

const classListActive = computed(() => props.isOpen ? 'what-to-wear-now-gallery-item__product-modal--active' : '');

const modalClassListModifiers = computed(() => [classListActive.value]);

function toggleDropdown () {
  emit('toggle')
}

</script>

<style lang="scss">
.what-to-wear-now-gallery-item {
  display: flex;
  flex-direction: column;
  gap: 13px;

  &__product {
    position: relative;
    overflow: hidden;

    &-img {
      width: 251.2px;
      height: 279px;

      @media (max-width: $mobile) {
        width: 195px;
        height: 218px;
      }
    }

    &-button {
      position: absolute;
      right: 15px;
      bottom: 15px;
      z-index: $z-index-1;
    }
  }

  &__info {
    display: flex;
    flex-direction: column;
    gap: 3px;
    font-size: 13px;
  }
}

.what-to-wear-now-gallery-item__product-modal {
  display: flex;
  flex-direction: column;
  gap: 16px;
  padding: 15px;
  background-color: rgba($color-white-1, 0.8);
  visibility: hidden;
  position: absolute;
  width: 100%;
  bottom: 0;
  left: 0;
  transform: translateY(100%);
  transition: all 0.4s ease;

  &--active {
    visibility: visible;
    transform: translateY(0);
    transition: all .4s ease;
  }

  &-title {
    font-size: 13px;
  }

  &-theme {
    display: flex;
    gap: 4px;

    &-item {
      width: 20px;
      height: 20px;
      border-radius: 50%;
      padding: 2px;
      display: flex;
      align-items: center;
      justify-content: center;

      &:hover {
        border: 1px solid $color-black-1;
      }

      &-color {
        background-color: $color-black-1;
        width: 16px;
        height: 16px;
        border-radius: 50%;
      }
    }
  }
}
</style>


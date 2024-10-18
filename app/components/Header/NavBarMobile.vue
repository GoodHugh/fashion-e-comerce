<template>
  <nav :class="classListModifiers" class="nav-bar-mobile">
    <ul class="nav-bar-mobile__list">
      <li class="nav-bar-mobile__list-item">
        <NuxtLink class="nav-bar-mobile__list-item-nav" to="#" @click="handleClick">
          <IconsUser />
        </NuxtLink>
      </li>
      <li class="nav-bar-mobile__list-item" v-for="item in dataNavbar">
        <NuxtLink class="nav-bar-mobile__list-item-nav" :to="item.url" @click="handleClick">
          {{ item.title }}
        </NuxtLink>
      </li>
    </ul>
  </nav>
</template>

<script lang="ts" setup>
interface Props {
  active: boolean;
}

interface Emits {
  (event: 'update:active', value: boolean): void;
}

const props = defineProps<Props>();
const emit = defineEmits<Emits>();

const clasListActive = computed(() => props.active ? 'nav-bar-mobile--active' : '');

const classListModifiers = computed(() => [clasListActive.value]);

const dataNavbar = {
  shop: {
    title: 'Shop',
    url: '#',
  },
  newArrivals: {
    title: 'New Arrivals',
    url: '#',
  },
  sales: {
    title: 'Sales',
    url: '#',
  },
  journel: {
    title: 'Journey',
    url: '#',
  },
  stores: {
    title: 'Stores',
    url: '#',
  }
}

function handleClick() {
  emit('update:active', false);
}
</script>

<style lang="scss">
.nav-bar-mobile {
  background-color: rgb($color-white-1, 0.5);
  position: fixed;
  width: 100%;
  left: -100%;
  transition: .4s ease;

  &--active {
    left: 0;
    transition: .4s ease;
  }

  &__list {
    display: flex;
    flex-direction: column;
    font-size: 13px;
    color: $color-white-1;
    gap: 1px;
  }

  &__list-item {
    display: flex;
    justify-content: center;
  }

  &__list-item-nav {
    width: 100%;
    padding: 20px 0;
    background-color: rgb($color-black-1, 0.8);
    text-align: center;
  }
}
</style>
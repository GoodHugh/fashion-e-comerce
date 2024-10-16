<template>
  <nav :class="classListModifiers" class="nav-bar-mobile">
    <ul class="nav-bar-mobile__list">
      <li class="nav-bar-mobile__list-item">
        <NuxtLink class="nav-bar-mobile__list-item-nav" to="/">
          <IconsUser />
        </NuxtLink>
      </li>
      <li class="nav-bar-mobile__list-item" v-for="item in dataNavbar">
        <NuxtLink class="nav-bar-mobile__list-item-nav" :to="item.url">
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

const props = defineProps<Props>();

const clasListActive = computed(() => props.active ? 'nav-bar-mobile--active' : '');

const classListModifiers = computed(() => [clasListActive.value]);

const dataNavbar = {
  shop: {
    title: 'Shop',
    url: '/shop',
  },
  newArrivals: {
    title: 'New Arrivals',
    url: '/new-arrivals',
  },
  sales: {
    title: 'Sales',
    url: '/sales',
  },
  journel: {
    title: 'Journey',
    url: '/journel',
  },
  stores: {
    title: 'Stores',
    url: '/stores',
  }
}
</script>

<style lang="scss">
.nav-bar-mobile {
  background-color: $color-white-1;
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
    padding: 16px 0;
    background-color: $color-black-1;
    opacity: 0.7;
    text-align: center;
  }
}
</style>
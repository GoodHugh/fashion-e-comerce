<template>
  <nav class="navbar">
    <ul class="navbar__list">
      <HeaderNavBarItem v-for="item in dataNavbar" :key="item.title" :title="item.title" :url="item.url" />
    </ul>
  </nav>
</template>

<script lang="ts" setup>
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
  }
}
</script>

<style lang="scss">
.navbar{
  @media (max-width: $mobile) {
    display: none;
  }

  &__list {
    display: flex;
  }
}
</style>
<template>
  <nav class="action-bar">
    <ul class="action-bar__list">
      <li class="action-bar__list-item">
        <IconsSearch />
      </li>
      <li class="action-bar__list-item">
        <NuxtLink to="#">Stores</NuxtLink>
      </li>
      <li class="action-bar__list-item">
        <NuxtLink to="#">
          <IconsUser />
        </NuxtLink>
      </li>
      <li class="action-bar__list-item">
        <NuxtLink class="action-bar__list-item-nav" to="#">
          <IconsHeart />
          <span class="action-bar__list-item-count">{{ 0 }}</span>
        </NuxtLink>
      </li>
      <li class="action-bar__list-item">
        <NuxtLink class="action-bar__list-item-nav" to="#">
          <IconsBag />
          <span>{{ 2 }}</span>
        </NuxtLink>
      </li>
    </ul>
  </nav>
</template>

<style lang="scss">
.action-bar {

   &__list {
     display: flex;
     gap: 18px;

     @media (max-width: $mobile) {
       gap: 13px;
     }
   }

    &__list-item {
     font-size: 13px;

      &:nth-child(2),
      &:nth-child(3) {
        @media (max-width: $mobile) {
          display: none;
        }
      }
    }

  &__list-item-nav {
    display: flex;
    align-items: center;
    gap: 4px;
  }
}
</style>
<script setup lang="ts">
</script>
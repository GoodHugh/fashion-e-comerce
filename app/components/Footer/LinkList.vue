<template>
  <section class="footer-link-list">
    <h3 class="footer-link-list__title">
      {{ props.title }}
    </h3>
    
    <ul class="footer-link-list__list">
      <li v-for="item in links" class="footer-link-list__list-item">
        <NuxtLink :to="item.url" class="footer-link-list__list-item-link">
          {{ item.title }}
        </NuxtLink>
      </li>
    </ul>
  </section>
</template>

<script setup lang="ts">

interface Props {
  title: string,
  links: Record<string, { title: string; url: string }>
}

const props = defineProps<Props>();
</script>

<style lang="scss">
.footer-link-list {
  display: flex;
  flex-direction: column;
  gap: 20px;
  width: 192px;

  &__title {
    font-size: 11px;
    text-transform: uppercase;
    color: $color-gray-2;
  }

  &__list {
    display: flex;
    flex-direction: column;
    gap: 4px;
    font-size: 13px;
    line-height: 20px;
  }
}
</style>
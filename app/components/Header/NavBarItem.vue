<template>
  <li class="navbar-item">
    <NuxtLink :to="props.url"> {{ props.title }} </NuxtLink>
  </li>
</template>

<script setup lang="ts">
interface Props {
  url: string;
  title: string;
}

const props = defineProps<Props>();
</script>

<style lang="scss">
.navbar-item {
  font-size: 13px;
  padding: 6px 21px;
}
</style>
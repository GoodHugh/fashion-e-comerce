<script setup lang="ts">
  interface Props {
    title: string
    theme: 'back' | 'white';
    handleClick?: () => void;
  }

  const props = withDefaults(defineProps<Props>(), {
    theme: 'white',
  });

  const classListTheme = computed(() => {
    switch (props.theme) {
      case 'back':
        return 'v-button--black';
      case 'white':
      default:
        return 'v-button--white';
    }
  })

  const classListModifiers = computed(() => [classListTheme.value]);
</script>

<template>
  <button class="v-button" :class="classListModifiers" @click="handleClick">
    <slot />
  </button>
</template>

<style lang="scss">
.v-button {
  padding: 11px 18px;
  font-size: 15px;
  display: inline-block;

  &--white {
    color: $color-black-1;
    background-color: $color-white-2;
  }
}
</style>
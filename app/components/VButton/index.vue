<script setup lang="ts">
  interface Props {
    theme?: 'back' | 'white';
    handleClick?: () => void;
    type?: 'text' | 'submit';
  }

  const props = withDefaults(defineProps<Props>(), {
    theme: 'white',
    type: 'text'
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
  <button class="v-button" :class="classListModifiers" @click.prevent="handleClick">
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

  &--black {
    color: $color-white-2;
    background-color: $color-black-1;
  }
}
</style>
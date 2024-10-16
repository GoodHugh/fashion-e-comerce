<template>
  <nav class="nav-burger">
    <button class="nav-burger__button" :class="classListModifiers" @click="toggleActive">
      <span></span>
      <span></span>
      <span></span>
    </button>
  </nav>
</template>

<script lang="ts" setup>

  interface Props {
    active: boolean;
  }

  interface Emits {
    (event: 'update:active', value: boolean): void;
  }

  const props = withDefaults(defineProps<Props>(), {
    active: false,
  })

  const emit = defineEmits<Emits>();

  const clasListActive = computed(() => props.active ? 'nav-burger__button--active' : '');

  const classListModifiers = computed(() => [clasListActive.value]);

  function toggleActive() {
    emit('update:active', !props.active);
  }
</script>

<style lang="scss">
.nav-burger {
  position: absolute;
  left: -1000px;

  @media (max-width: $mobile) {
    position: static;
    left: 0;
  }

  &__button {
    height: 20px;
    width: 20px;
    position: relative;

    > span {
      height: 1px;
      width: 100%;
      background-color: $color-black-1;
      border-radius: 25px;
      position: absolute;
      left: 50%;
      top: 50%;
      transform: translate(-50%, -50%);
      transition: .3s ease;

      &:nth-child(1) {
        top: 25%;
      }

      &:nth-child(3) {
        top: 75%;
      }
    }

    &--active {

      > span:nth-child(1) {
        top: 50%;
        transform: translate(-50%, -50%) rotate(45deg);
      }

      > span:nth-child(2) {
        opacity: 0;
      }

      > span:nth-child(3) {
        top: 50%;
        transform: translate(-50%, -50%) rotate(-45deg);
      }
    }
  }
}

</style>
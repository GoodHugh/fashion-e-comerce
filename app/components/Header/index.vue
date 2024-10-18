<template>
  <header>
    <div class="header__container">
      <div class="header__bar">
        <HeaderNavBurger v-model:active="isActive" />
        <HeaderVLogo />
        <HeaderNavBar />
        <HeaderActionBar class="header__bar-last-item" />
      </div>
    </div>
    <HeaderNavBarMobile v-model:active="isActive" />
  </header>
</template>

<script lang="ts" setup>
const isActive = ref<boolean>(false);
</script>

<style lang="scss">
.header {
  &__bar {
    position: relative;
    height: 68px;
    display: flex;
    align-items: center;

    @media (max-width: $mobile) {
      height: 50px;
    }
  }

  &__bar-last-item {
    margin-left: auto;
  }
}
</style>
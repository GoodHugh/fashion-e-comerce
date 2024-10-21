<template>
  <nav class="v-logo">
    <NuxtLink to="/">
      <IconsLogo class="logo"/>
    </NuxtLink>
  </nav>
</template>

<style lang="scss">
.v-logo {
  @media (max-width: $mobile) {
    position: absolute;
    left: 50%;
    top: 50%;
    transform: translate(-50%, -50%);
  }
}
</style>
<template>
  <section class="contact-us">
    <h3 class="contact-us__title">CONTACT US</h3>
    <ul class="contact-us__list">
      <li class="contact-us__list-item">
        <NuxtLink to="tel:+18443266000">
          +1 (844) 326-6000
        </NuxtLink>
      </li>
      <li class="contact-us__list-item">
        <NuxtLink to="mailto:test@example.com">
          Email Us
        </NuxtLink>
      </li>
      <li class="contact-us__list-item">
        Mon-Fri 9am-3pm PT
      </li>
    </ul>
  </section>
</template>

<script setup lang="ts">

</script>

<style lang="scss">
.contact-us {
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
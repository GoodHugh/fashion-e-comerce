<template>
  <section class="subscribe-form">
    <p class="subscribe-form__title">Get the latest new from us</p>
    <form class="subscribe-form__form" action="#" method="POST">
      <input class="subscribe-form__form-input" type="email" placeholder="Enter your email address" required>
      <p class="subscribe-form__form-terms">
        By signing up, you agree to our
        <NuxtLink class="subscribe-form__form-terms-link" to="#">Privacy Policy</NuxtLink> and
        <NuxtLink class="subscribe-form__form-terms-link" to="#">Terms of Service</NuxtLink>.
      </p>
      <VButton class="subscribe-form__form-button" theme="back" type="submit">Subscribe</VButton>
    </form>
  </section>
</template>

<script setup lang="ts">

</script>

<style lang="scss">
.subscribe-form {
  max-width: 491px;
  display: flex;
  flex-direction: column;
  gap: 24px;
  padding-right: 25px;

  &__form {
    display: flex;
    flex-direction: column;
    gap: 5px;
  }


  &__form-input {
    border: 1px solid $color-gray-3;
    padding: 12px 14px;
    font-size: 13px;
    background-color: #DDDDDD;
  }

  &__form-terms {
    font-size: 13px;
    line-height: 20px;
  }

  &__form-terms-link {
    text-decoration: underline !important;
  }

  &__form-button {
    align-self: flex-start;
  }
}
</style>
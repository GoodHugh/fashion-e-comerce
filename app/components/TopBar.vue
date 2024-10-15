<template>
  <div class="top-bar">
    <div class="top-bar__container">
      <p class="top-bar__container-item" />
    </div>
  </div>
</template>

<style lang="scss">
.top-bar {
  background-color: $color-black-1;
}

.top-bar__container {
  display: flex;
  align-items: center;
  justify-content: center;
}

.top-bar__container-item {
  color: $color-white-1;
  font-size: 11px;
  padding: 12px 0;

  &::after {
    content: 'Complimentary U.S. No-Rush Shipping on orders of $95 or more. Shop now';

    @media (max-width: $minWidth + px) {
      content: "The Archive Sale is live. Starting at 20% off. Shop now.";
    }
  }
}
</style>
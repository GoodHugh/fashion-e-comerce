<template>
  <footer class="footer">
    <div class="footer__container">
      <div class="footer__info">
        <div class="footer__info-first-section">
          <FooterContactUs />
          <FooterLinkList title="CUSTOMERS" :links="customersData" />
          <FooterLinkList title="COMPANY" :links="companyData" />
        </div>
        <div class="footer__info-last-section">
          <FooterSubscribeForm />
        </div>
      </div>
      <p class="footer__copyright">
        ©CEIN
      </p>
    </div>
  </footer>
</template>

<script setup lang="ts">
const customersData = {
  startAReturn: {
    title: 'StartAReturn',
    url: '#'
  },
  returnPolicy: {
    title: 'ReturnPolicy',
    url: '#',
  },
  faq: {
    title: 'FAQ',
    url: '#'
  },
  catalogsAndMailers: {
    title: 'Catalogs and Mailers',
    url: '#',
  },
  aboutGroupGifting: {
    title: 'About Group Gifting',
    url: '#'
  }
}

const companyData = {
  aboutUs: {
    title: 'About Us',
    url: '#'
  },
  sustainability: {
    title: 'Sustainability',
    url: '#'
  },
  discoverRevive: {
    title: 'Discover Revive',
    url: '#'
  },
  careers: {
    title: 'Careers',
    url: '#'
  },
  privacyPolicy: {
    title: 'Privacy Policy',
    url: '#'
  },
  terms: {
    title: 'Terms',
    url: '#'
  }
}
</script>

<style lang="scss">
.footer {
  padding: 42px 0;
  background-color: #DDDDDD;

  &__container {
    display: flex;
    flex-direction: column;
    gap: 80px;
  }

  &__info{
    display: flex;
    justify-content: space-between;
    gap: 25px;
    padding-top: 34px;

    @media (max-width: $pc) {
      flex-direction: column;
      gap: 48px;
    }
  }

  &__info-first-section {
    width: 100%;
    display: flex;
    gap: 25px;

    @media (max-width: $mobile) {
      flex-direction: column;
      gap: 48px;
    }
  }

  &__info-last-section {
    width: 100%;
    display: flex;
    flex-direction: column;
    align-items: flex-end;


    @media (max-width: $pc) {
      align-items: flex-start;
    }
  }

  &__copyright {
    font-size: 13px;
  }
}
</style>
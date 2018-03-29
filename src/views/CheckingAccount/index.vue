<template>
<div class="body" v-if="QR">
  <h4 class="checking-acount-header">Checking Account</h4>
  <div class="hero-image">
    <h3 class="heading">Everyday Checking</h3>
    <div class="sub-header">Banking made easy. Open with $25.</div>
    <div class="text-link">How to avoid the $10 monthly service fee</div>
    <div class="text-link">Common fees for this account (PDF)</div>
    <div @click='authorizeUser()' class="open-checking-account verified w-button">Open with bankID</div>
    <div class="open-checking-account w-button">Go to Form</div>
    <div class="details-text">Everyday Checking Details &gt;</div>
  </div><a class="compare-acounts-button w-button">Compare All Accounts</a>
  <h3 class="heading-2">Checking Account Benefits</h3>
  <div class="convenience-section">
    <h3 class="convenience-header">Convenience and Control</h3>
    <p>Our mobile banking app puts you in control of your accounts.</p>
    <div class="more-link">More Checking Accounts &gt;</div>
  </div>
  </div>
</template>
<script>
  import { mapActions, mapState } from 'vuex';

  export default {
    name: 'CheckingAccount',
    computed: {
      ...mapState([
        'QR',
      ]),
    },
    methods: {
      ...mapActions([
        'getSignInQRCode',
      ]),
      authorizeUser() {
        this.$store.dispatch('authorizeUser');
      },
    },
    mounted() {
      this.getSignInQRCode();
    },
  };
</script>

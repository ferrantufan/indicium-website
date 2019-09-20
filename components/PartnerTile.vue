<template>
  <a :href="'/partners/' + partner.slug" class="inner-container">
    <div class="logo-container">
      <div class="logo" :style="'background-image: url(' + partner.logoUrl + ')'"></div>
    </div>
    <div class="text">
      {{ partner.name }}
    </div>
  </a>
</template>

<script>
export default {
  name: 'PartnerTile',
  props: {
    partner: {
      type: Object,
      required: true
    }
  }
}
</script>

<style scoped lang="scss">
  @import "../assets/scss/variables";

  .text {
    display: none;
  }

  .inner-container {
    display: flex;
    flex-direction: column;
    width: calc(33% - 30px);
    height: 100%;
    padding: 40px 10px;
    @media screen and (max-width: $bp-tablet-md) {
      width: calc(50% - 20px);
    }
    @media screen and (max-width: $bp-mobile-lg) {
      width: 100%;
    }

    &:hover .text {
      display: block;
    }
  }

  .logo-container {
    width: 100%;
    position: relative;
    min-height: 180px;
    max-width: 300px;
    display: flex;
    align-items: center;
  }

  .logo {
    position: absolute;
    top: 40px;
    bottom: 40px;
    left: 40px;
    right: 40px;
    background-position: center;
    background-size: contain;
    background-repeat: no-repeat;
  }
</style>

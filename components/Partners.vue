<template>
  <div class="partners">
    <h5 class="center">
      Partners
    </h5>
    <slick
      :options="slickOptions"
    >
      <img v-for="(s, idx) in partners" :key="idx" :src="s.logoUrl" alt="partner logo title" />
    </slick>
  </div>
</template>

<script>

import content from '../content'

export default {
  name: 'Partners',
  data: () => ({
    slickOptions: {
      initialSlide: 2,
      slidesToShow: 5,
      variableWidth: true,
      slidesToScroll: 1,
      centerMode: true,
      responsive: [{
        breakpoint: 1100,
        settings: {
          centerMode: false,
          initialSlide: 0,
          slidesToShow: 2,
          autoplay: true,
          prevArrow: false,
          nextArrow: false,
        }
      }]
    },
    partners: content.partners
  })
}
</script>

<style lang="scss">
@import '../assets/scss/variables.scss';

.partners {
  background: #fff;
  box-shadow: inset 0 -1px 0 0 #C6D1E0, inset 0 1px 0 0 #C6D1E0;
  padding: 8px 0 32px;
  overflow: hidden;

  @media screen and (max-width: $bp-tablet-sm) {
    padding: 8px 0 12px;
  }

  h5 {
    margin-bottom: 16px;
  }

  .slick-slider {
    // width: 90%;
    margin: 0 auto;
    box-sizing: border-box;
    position: relative;

    @media screen and (max-width: $bp-tablet-sm) {
      width: 100%;
    }

    .slick-arrow {
      display: none;
      position: absolute;
      bottom: 0;
      left: 0;
      color: var(--text-color);

      &.slick-next {
        left: auto;
        right: 0
      }

    }

    .slick-track {
      display: flex;
      align-items: center;

      .slick-slide {
        width: 128px;
        padding: 0 32px;
        display: inline-flex;
        justify-content: center;
      }
    }
  }
}
</style>

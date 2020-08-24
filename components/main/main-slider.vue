<template>
  <div class="mx-n2_5 mx-xl-0">
    <Swiper
      ref="swiperComponent"
      :options="swiperOptions"
      :class="{
        'slider-container main-slider mx-auto mt-2 mt-xl-4_75 mb-0 mb-xl-6_75 px-2_5 px-xl-0 pb-7 pb-xl-0': true,
      }"
      class=""
    >
      <SwiperSlide class="slider-slide text-center flex align-items-center justify-content-center position-relative" v-for="slide in slides" :key="slide.image">
        <div class="embed-responsive slider-slide-embed rounded-xl">
          <a class="stretched-link" :href="slide.url">
            <picture class="w-100 h-100">
              <source :srcset="slide.image" type="image/jpg" media="(min-width: 768px)">
              <source :srcset="slide.imageMobile" type="image/jpg">
              <img class="embed-responsive-item cover-object" :src="slide.image" loading="lazy" />
            </picture>
          </a>
        </div>
      </SwiperSlide>
      <div
        :class="{
          'swiper-pagination slider-pagination d-xl-none': true,
          'mb-2_5': $device.isDesktopOrTablet,
          'slider-pagination-mobile mb-2_5': $device.isMobile,
        }"
        slot="pagination"></div>
      <div class="swiper-button-prev slider-prev w-7_25 h-7_25 rounded-pill" title="Назад" slot="button-prev" v-if="$device.isDesktopOrTablet">
        <svgicon class="text-white w-3 h-3" name="chevron-left" />
      </div>
      <div class="swiper-button-next slider-next w-7_25 h-7_25 rounded-pill" title="Вперед" slot="button-next" v-if="$device.isDesktopOrTablet">
        <svgicon class="text-white w-3 h-3" name="chevron-right" />
      </div>
    </Swiper>
  </div>
</template>

<script>
  import { Swiper, SwiperSlide, directive } from 'vue-awesome-swiper';
  import 'swiper/css/swiper.css';
  import '@/components/icons/chevron-left';
  import '@/components/icons/chevron-right';

  export default {
    data() {
      return {
        slides: [
          { image: "/images/banner-01-desktop.jpg", imageMobile: "/images/banner-01-mobile.jpg", url: "#" },
          { image: "/images/banner-01-desktop.jpg", imageMobile: "/images/banner-01-mobile.jpg", url: "#" },
          { image: "/images/banner-01-desktop.jpg", imageMobile: "/images/banner-01-mobile.jpg", url: "#" },
        ],
        swiperOptions: {
          effect: 'coverflow',
          loop: true,
          grabCursor: true,
          centeredSlides: true,
          slidesPerView: 1,
          spaceBetween: 20,
          slideToClickedSlide: true,
          noSwiping: true,
          coverflowEffect: {
            rotate: 0,
            stretch: 0,
            depth: 0,
            modifier: 1,
            slideShadows : false,
          },
          breakpoints: {
            1200: {
              slidesPerView: 2,
              spaceBetween: 0,
              coverflowEffect: {
                rotate: 0,
                stretch: 240,
                depth: 100,
                modifier: 1,
                slideShadows : false,
              },
            }
          },
          pagination: {
            el: '.swiper-pagination',
          },
          navigation: {
            nextEl: '.swiper-button-next',
            prevEl: '.swiper-button-prev',
          },
        }
      }
    },
    computed: {
      swiper() {
        return this.$refs.mySwiper.$swiper;
      }
    },
    mounted() {
      // console.log('Current Swiper instance object', this.swiper)
      // this.swiper.slideTo(3, 1000, false)
    },
    components: {
      Swiper,
      SwiperSlide,
    },
    directives: {
      swiper: directive,
    }
  }
</script>

<style lang="scss">
  .main-slider {
    max-width: 1404px;

    .slider-slide {
      width: calc(100% / 2);

      @media (max-width: 1200px) {
        width: 100%;
      }

      &:not(.swiper-slide-active) .stretched-link {
        pointer-events: none !important;
      }
    }

    .slider-slide-embed {
      transition: all .2s;
      transform: scale(.7);

      &::before {
        padding-top: percentage(311 / 702);
      }

      .embed-responsive-item {
        filter: blur(5px);

        @media (max-width: 1200px) {
          filter: none;
        }
      }
    }

    .slider-slide.swiper-slide-active .slider-slide-embed {
      transform: scale(1);

      .embed-responsive-item {
        filter: none;
      }
    }

    .slider-slide.swiper-slide-prev .slider-slide-embed,
    .slider-slide.swiper-slide-next .slider-slide-embed, {
      transform: scale(.85);

      @media (max-width: 1200px) {
        transform: scale(1);
      }
    }

    .slider-prev,
    .slider-next {
      margin-top: calc(-1 * 3.625rem / 2);

      @media (max-width: 1200px) {
        margin-top: calc(-1 * 3.625rem / 2 + -1 * 3.5rem / 2);
      }
    }

    .slider-prev {
      left: calc(25% - 1.8125rem);

      @media (max-width: 1200px) {
        left: 1.25rem;
      }
    }

    .slider-next {
      right: calc(25% - 1.8125rem);

      @media (max-width: 1200px) {
        right: 1.25rem;
      }
    }
  }
</style>

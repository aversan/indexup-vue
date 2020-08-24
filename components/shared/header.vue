<template>
  <b-navbar
    :class="{
      'header flex-row flex-nowrap font-weight-medium overflow-hidden': true,
      'h-10': $device.isDesktopOrTablet,
      'header-mobile h-12': $device.isMobile
    }"
    sticky type="dark"
    tag="header"
    variant="black"
  >
    <b-container class="px-2_5 px-xl-4" fluid>
      <b-navbar-brand class="mr-2 mr-xxl-3_75 mt-n1" href="">
        <IndexUpLogo class="header-logo" />
        <span class="sr-only">IndexUp</span>
      </b-navbar-brand>
      <div class="mx-2 mx-xxl-3_75 text-nowrap" v-if="$device.isDesktopOrTablet">
        <span class="navbar-text mr-2 d-none d-xl-inline">Приложение</span>
        <AndroidButton class="header-button mr-0_5" />
        <IOSButton class="header-button mr-0_5" />
      </div>
      <a class="btn px-2_5 py-1_25 border border-white-10 d-inline-flex align-items-center mx-2 mx-xxl-3_75 font-weight-medium text-sm-2" href="" v-if="$device.isDesktopOrTablet">
        <svgicon class="text-blue mr-1_75" name="lock" />
        Доступ к сайту
      </a>
      <div class="flex-grow-1"></div>
      <div class="overflow-hidden mw-100 h-10" v-if="$device.isDesktopOrTablet">
        <div class="nav header-nav flex-nowrap mb-0 pb-4 overflow-x-auto scrolling-touch text-nowrap">
          <a class="nav-link py-1_5 px-2 px-xxl-3_75 h-10 d-flex align-items-center header-link active" href="">Главная</a>
          <a class="nav-link py-1_5 px-2 px-xxl-3_75 h-10 d-flex align-items-center header-link" href=""><span class="svg-icon svg-icon-online mr-1_25"></span>Live</a>
          <a class="nav-link py-1_5 px-2 px-xxl-3_75 h-10 d-flex align-items-center header-link text-uppercase" href="">О Index</a>
        </div>
      </div>
      <div class="flex-grow-1" v-if="$device.isDesktopOrTablet"></div>
      <div class="ml-2 ml-xxl-3_75 d-flex align-items-center flex-nowrap">
        <b-button
          :class="{
            'header-button px-2_5 px-xxl-5 h-6 btn': true,
            'text-sm': $device.isDesktopOrTablet,
            'text-lg': $device.isMobile
          }"
          variant="dark"
          href=""
        >
          Войти
        </b-button>
        <button
          :class="{
            'header-button px-2_5 px-xxl-5 h-6 btn btn-gradient-green ml-1': true,
            'text-sm': $device.isDesktopOrTablet,
            'text-lg': $device.isMobile
          }"
          href=""
        >
          Регистрация
        </button>
      </div>
    </b-container>
  </b-navbar>
</template>
<script>
  import IndexUpLogo from '@/components/shared/index-up-logo';
  import AndroidButton from '@/components/shared/android-button';
  import IOSButton from '@/components/shared/ios-button';
  import '@/components/icons/lock';

  export default {
    components: {
      IndexUpLogo,
      AndroidButton,
      IOSButton,
    }
  }
</script>

<style lang="scss">
  .header {
    font-size: .9375rem;
    border-bottom: 1px solid var(--gray-975) !important;

    &-nav {
      position: absolute;
      left: 50%;
      transform: translateX(-50%);

      @media (max-width: 1920px) {
        & {
          position: static;
          left: 0;
          transform: translateX(0);
        }
      }
    }

    &-link.active {
      position: relative;
    }

    &-link.active::before {
      content: '';
      height: .375rem;
      border-radius: 1rem;
      background-image: linear-gradient(26.85deg, #EE2B31 6.44%, #9E1215 87.71%);
      position: absolute;
      bottom: 0;
      left: 1.5rem;
      right: 1.5rem;

      @media (max-width: 1440px) {
        left: .5rem;
        right: .5rem;
      }
    }
  }

  .header-mobile {
    .header-logo {
      height: 2rem;
      width: auto;
    }
  }
</style>

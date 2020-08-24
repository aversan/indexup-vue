<template>
  <div
    :class="{
      'bg-gray-200 text-gray-950 bet-forecast d-flex w-100 align-items-stretch rounded-xl': true,
      'bet-forecast-mobile': $device.isMobile,
    }"
  >
    <div
      :class="{
        'bet-forecast-title font-weight-semibold d-flex align-items-center flex-grow-1': true,
        'text-sm leading-tighter': $device.isDesktopOrTablet,
        'text-3xl leading-tight': $device.isMobile,
      }"

    >
      {{ text }}
    </div>
    <BetFactor factor="1.5" oldFactor="1.4" percent="13" />
  </div>
</template>

<script>
  import BetFactor from '@/components/bet/bet-factor';

  export default {
    components: {
      BetFactor,
    },
    props: {
      text: {
        type: String,
        default: '',
      },
    },
  }
</script>

<style lang="scss">
  .bet-forecast {
    &-title {
      padding-left: 1.25rem;
      padding-right: .625rem;
    }
  }

  .bet-forecast-mobile {
    padding-top: .625rem;
    padding-bottom: .625rem;
    padding-right: .625rem;

    .bet-forecast-title {
      padding-left: 1.875rem;
      padding-right: 1.25rem;
    }
  }
</style>

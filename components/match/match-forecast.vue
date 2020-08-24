<template>
  <b-card
    no-body
    tag="section"
    :class="{
      'match-forecast': true,
      'my-1_25': $device.isDesktopOrTablet,
      'match-forecast-mobile my-2': $device.isMobile,
    }"
    bg-variant="transparent"
  >
    <b-card-header
      header-tag="header"
      header-bg-variant="dark"
      header-text-variant="white"
      role="tab"
      class="match-forecast-header position-relative text-truncate d-flex align-items-center"
      v-b-toggle.match-collapse-02
    >
      <div class="flex-grow-1">
        <div
          :class="{
          'match-forecast-title font-weight-semibold': true,
          'text-base': $device.isDesktopOrTablet,
          'text-3xl leading-tight': $device.isMobile,
        }"
        >
          Азиатская фора. Основное время
        </div>
      </div>
      <svgicon class="text-primary match-forecast-icon" name="chevron-down" />
    </b-card-header>
    <b-collapse id="match-collapse-02" visible role="tabpanel">
      <b-card-body class="match-forecast-container overflow-hidden rounded-b-xl" body-bg-variant="white">
        <b-row cols="1" cols-md="2" no-gutters>
          <b-col class="match-forecast-item d-flex">
            <BetForecast text="Манчестер Юн. (+1,5)" />
          </b-col>
          <b-col class="match-forecast-item d-flex">
            <BetForecast text="Манчестер Юн. (+1,5)" />
          </b-col>
          <b-col class="match-forecast-item d-flex">
            <BetForecast text="Манчестер Юн. (+1,5)" />
          </b-col>
          <b-col class="match-forecast-item d-flex">
            <BetForecast text="Манчестер Юн. (+1,5)" />
          </b-col>
        </b-row>
      </b-card-body>
    </b-collapse>
  </b-card>
</template>

<script>
  import BetForecast from '@/components/bet/bet-forecast';
  import '@/components/icons/chevron-down';

  export default {
    components: {
      BetForecast,
    },
  }
</script>

<style lang="scss">
  .match-forecast {
    .match-forecast-icon {
      width: .75rem;
      height: .75rem;
      transition: all .2s ease-in-out;
      transform: rotate(180deg);
    }

    .match-forecast-header.collapsed {
      border-radius: 10px;
    }

    .match-forecast-header.collapsed .match-forecast-icon {
      transform: rotate(0deg);
    }

    .match-forecast-container,
    .match-forecast-item {
      padding: .3125rem;
    }
  }

  .match-forecast-mobile {
    .match-forecast-container,
    .match-forecast-item {
      padding: .5rem;
    }

    .match-forecast-header {
      height: 5.5rem;
    }

    .match-forecast-icon {
      width: 1.5rem;
      height: 1.5rem;
    }
  }
</style>

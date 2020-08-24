<template>
  <b-card
    no-body
    tag="section"
    :class="{
      'match-forecast-main': true,
      'my-1_25': $device.isDesktopOrTablet,
      'match-forecast-main-mobile my-2': $device.isMobile,
    }"
    bg-variant="transparent"
  >
    <b-card-header
      header-tag="header"
      header-bg-variant="dark"
      header-text-variant="white"
      role="tab"
      class="match-forecast-main-header position-relative text-truncate d-flex align-items-center"
      v-b-toggle.match-collapse-01
    >
      <div class="flex-grow-1">
        <div
          :class="{
            'match-forecast-main-title font-weight-semibold': true,
            'text-base': $device.isDesktopOrTablet,
            'text-3xl leading-tight': $device.isMobile,
          }"
        >
          Результат. Основное время
        </div>
      </div>
      <svgicon class="text-primary match-forecast-main-icon" name="chevron-down" />
    </b-card-header>
    <b-collapse id="match-collapse-01" visible role="tabpanel">
      <b-card-body class="match-forecast-main-container overflow-hidden rounded-b-xl" body-bg-variant="white">
        <b-row cols="1" cols-md="2" cols-xl="3" no-gutters>
          <b-col class="match-forecast-main-item d-flex">
            <BetForecast text="Манчестер Юн. победа" />
          </b-col>
          <b-col class="match-forecast-main-item d-flex">
            <BetForecast text="Ничья" />
          </b-col>
          <b-col class="match-forecast-main-item d-flex">
            <BetForecast text="Челси победа" />
          </b-col>
          <b-col class="match-forecast-main-item d-flex">
            <BetForecast text="Манчестер Юн. не проиграет" />
          </b-col>
          <b-col class="match-forecast-main-item d-flex">
            <BetForecast text="Не будет нечьи" />
          </b-col>
          <b-col class="match-forecast-main-item d-flex">
            <BetForecast text="Челси не проиграет" />
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
  .match-forecast-main {
    .match-forecast-main-icon {
      width: .75rem;
      height: .75rem;
      transition: all .2s ease-in-out;
      transform: rotate(180deg);
    }

    .match-forecast-main-header.collapsed {
      border-radius: 10px;
    }

    .match-forecast-main-header.collapsed .match-forecast-main-icon {
      transform: rotate(0deg);
    }

    .match-forecast-main-container,
    .match-forecast-main-item {
      padding: .3125rem;
    }
  }

  .match-forecast-main-mobile {
    .match-forecast-main-header {
      height: 5.5rem;
    }

    .match-forecast-main-container,
    .match-forecast-main-item {
      padding: .5rem;
    }

    .match-forecast-main-icon {
      width: 1.5rem;
      height: 1.5rem;
    }
  }
</style>

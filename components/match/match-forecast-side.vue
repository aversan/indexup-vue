<template>
  <b-card
    no-body
    tag="section"
    :class="{
      'match-forecast-side my-4_75': true,
    }"
    bg-variant="transparent"
  >
    <b-card-header
      header-tag="header"
      header-bg-variant="dark"
      header-text-variant="white"
      role="tab"
      class="match-forecast-side-header text-truncate d-flex align-items-center"
      v-b-toggle.match-collapse-01
    >
      <div class="flex-grow-1">
        <div
          :class="{
            'match-forecast-side-title font-weight-semibold': true,
            'text-base': $device.isDesktopOrTablet,
          }"
        >
          Испания. Премьер-Лига
        </div>
      </div>
      <svgicon class="text-white match-forecast-side-icon-left clickable w-1_5 h-1_5" name="chevron-left-bold" />
      <svgicon class="text-white match-forecast-side-icon-right clickable w-1_5 h-1_5 ml-2" name="chevron-right-bold" />
    </b-card-header>
    <b-card-body class="match-forecast-side-body p-0 rounded-b-xl overflow-hidden">
      <MatchTableSide />
    </b-card-body>
  </b-card>
</template>

<script>
  import MatchTableSide from '@/components/match/match-table-side';
  import '@/components/icons/chevron-left-bold';
  import '@/components/icons/chevron-right-bold';

  export default {
    components: {
      MatchTableSide,
    },
  }
</script>

<style lang="scss">
  .match-forecast-side {
  }
</style>

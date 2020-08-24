<template>
  <b-table-simple
    table-variant="white"
    borderless
    :class="{
      'match-table': true,
      'mt-1 mb-4_75': $device.isDesktopOrTablet,
      'match-table-mobile mb-2': $device.isMobile,
    }"
    table-class="rounded-xl mb-0"
    responsive
  >
    <colgroup>
      <col width="100" v-if="$device.isDesktopOrTablet">
      <col width="auto" v-if="$device.isDesktopOrTablet">
      <col width="100" v-if="$device.isDesktopOrTablet">
      <col width="1">
      <col width="1">
      <col width="1">
      <col width="10" v-if="$device.isDesktopOrTablet">
      <col width="120" v-if="$device.isDesktopOrTablet">
      <col width="10" v-if="$device.isDesktopOrTablet">
    </colgroup>
    <MatchTableHeader />
    <MatchTableBody />
  </b-table-simple>
</template>

<script>
  import MatchTableHeader from '@/components/match/match-table-header';
  import MatchTableBody from '@/components/match/match-table-body';

  export default {
    components: {
      MatchTableHeader,
      MatchTableBody,
    }
  }
</script>

<style lang="scss">
  .match-table {
    .match-table-cell {
      padding-left: 15px;
      padding-right: 15px;

      &.cell-date {
        padding-left: 30px;
      }
    }

    .match-table-cell.cell-hr,
    .match-table-cell.cell-vr {
      font-size: 0;
    }

    .match-table-cell.cell-vr {
      min-width: .625rem;
    }
  }

  .match-table-mobile {
    .match-table-cell {
      padding-left: 10px;
      padding-right: 10px;

      &:first-child {
        padding-left: 20px;
      }

      &:last-child {
        padding-right: 20px;
      }
    }

  }

</style>

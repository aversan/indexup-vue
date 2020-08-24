<template>
  <b-thead
    :class="{
      'match-table-header': true,
      'match-table-header-mobile': $device.isMobile,
    }"
  >
    <b-tr class="match-table-row" v-if="$device.isMobile">
      <b-th class="match-table-cell cell-match-mobile text-truncate bg-white text-gray-700 cell-match" colspan="3">
        <MatchInfo layout="side" variant="text" />
      </b-th>
    </b-tr>
    <b-tr class="match-table-row">
      <b-th class="match-table-cell font-weight-semibold text-truncate text-center bg-dark text-white" v-if="$device.isDesktopOrTablet">Дата</b-th>
      <b-th class="match-table-cell font-weight-semibold text-truncate text-center bg-dark text-white" v-if="$device.isDesktopOrTablet">Событие</b-th>
      <b-th class="match-table-cell font-weight-semibold text-center text-truncate bg-dark text-white" v-if="$device.isDesktopOrTablet"></b-th>
      <b-th class="match-table-cell font-weight-semibold text-center text-truncate bg-dark text-white" title="Победа 1">П1</b-th>
      <b-th class="match-table-cell font-weight-semibold text-center text-truncate bg-dark text-white" title="Ничья">X</b-th>
      <b-th class="match-table-cell font-weight-semibold text-center text-truncate bg-dark text-white" title="Победа 2">П2</b-th>
      <b-th class="match-table-cell font-weight-semibold text-center text-truncate bg-dark text-white cell-vr p-0" v-if="$device.isDesktopOrTablet"></b-th>
      <b-th class="match-table-cell font-weight-semibold text-center text-truncate bg-dark text-white" v-if="$device.isDesktopOrTablet"></b-th>
      <b-th class="match-table-cell font-weight-semibold text-center text-truncate bg-dark text-white cell-vr p-0" v-if="$device.isDesktopOrTablet"></b-th>
    </b-tr>
  </b-thead>
</template>

<script>
  import MatchInfo from '@/components/match/match-info';

  export default {
    components: {
      MatchInfo,
    }
  }
</script>

<style lang="scss">
  .match-table-header {
    .match-table-cell {
      font-size: .9375rem;

      &:first-child,
      &:last-child {
        position: relative;
      }

      &:first-child::before,
      &:first-child::after,
      &:last-child::before,
      &:last-child::after {
        position: absolute;
        content: "";
        width: 10px;
        height: 10px;
        overflow: hidden;
        background-image: url('data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAABQAAAAUCAIAAAAC64paAAAACXBIWXMAAA7EAAAOxAGVKw4bAAAAz0lEQVQ4jZ2Uy3LDIAxFjySwm5mu+v8/ikGQhR+1nTS1uSuG4eiBNFf4/uEkC1hADBGA1miOF7ycHoYzFkdED5cioFikVXLahzCGx3KMI/FryfZWIlhEhOrzhf6SYfgTO9Q6EMcdbOEqufEWVniNdENxBBQL5x+6IlEs6FxAjywoYp2wmH6azT9wR7c7Ka11oq0pzXth19d1vyovihdavZ+24kUBcroN58Synl4o0w2yTHOz66hyusqXaat0t5s5Uf2NGWx6MYPjYs9ec9mGnvINTmRaucCbAAAAAElFTkSuQmCC');
      }

      &:first-child::before {
        top: 0;
        left: 0;
        background-position: 0 0;
      }

      &:first-child::after {
        bottom: 0;
        left: 0;
        background-position: 0 100%;
      }

      &:last-child::before {
        top: 0;
        right: 0;
        background-position: 100% 0;
      }

      &:last-child::after {
        bottom: 0;
        right: 0;
        background-position: 100% 100%;
      }
    }
  }

  .match-table-header-mobile {
    .match-table-cell {
      font-size: .875rem;
      line-height: 1.2;
      padding-top: .3125rem;
      padding-bottom: .3125rem;

      &.cell-match {
        padding-top: .625rem;
        padding-bottom: .625rem;
      }

      &:first-child::before,
      &:first-child::after,
      &:last-child::before,
      &:last-child::after {
        display: none;
      }
    }
  }
</style>

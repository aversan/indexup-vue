<template>
  <b-tbody
    :class="{
      'match-table-body bg-white text-gray-950': true,
      'match-table-body-mobile': $device.isMobile,
    }"
  >
    <b-tr class="match-table-row h-1" v-if="$device.isDesktopOrTablet">
      <b-td class="match-table-cell cell-hr p-0 bg-black" colspan="9"></b-td>
    </b-tr>
    <b-tr class="match-table-row first h-1_25" v-if="$device.isDesktopOrTablet">
      <b-td class="match-table-cell cell-hr p-0" colspan="9"></b-td>
    </b-tr>
    <b-tr class="match-table-row" v-if="$device.isMobile">
      <b-th class="match-table-cell align-middle font-weight-semibold text-xl" colspan="3">
        Мы нашли:
      </b-th>
    </b-tr>
    <b-tr class="match-table-row">
      <b-td class="match-table-cell text-center align-middle cell-date" rowspan="2" v-if="$device.isDesktopOrTablet">
        <strong class="text-xl time d-block">21:00</strong>
        <small class="text-sm font-weight-medium text-gray-525 d-block day">Сегодня</small>
      </b-td>
      <b-td class="match-table-cell align-middle text-center cell-match" rowspan="2" v-if="$device.isDesktopOrTablet">
        <MatchInfo variant="short-small" />
      </b-td>
      <b-th class="match-table-cell align-middle font-weight-semibold text-lg text-white bg-red-500 rounded-tl-xl" v-if="$device.isDesktopOrTablet">
        Мы нашли
      </b-th>
      <b-td class="match-table-cell cell-bet text-center align-middle">
        <BetFactor factor="1.5" percent="13" outline />
      </b-td>
      <b-td class="match-table-cell cell-bet text-center align-middle">
        <BetFactor factor="1.5" percent="13" outline />
      </b-td>
      <b-td
        :class="{
          'match-table-cell cell-bet text-center align-middle': true,
          'rounded-tr-xl': $device.isDesktopOrTablet,
        }"
      >
        <BetFactor factor="1.5" percent="13" outline />
      </b-td>
      <b-td class="match-table-cell p-0 cell-vr w-1_25" rowspan="2" v-if="$device.isDesktopOrTablet"></b-td>
      <b-td class="match-table-cell text-center align-middle font-weight-bold text-base text-primary bg-gray-200 cell-count rounded-xl" rowspan="2" v-if="$device.isDesktopOrTablet">
        +1245
      </b-td>
      <b-td class="match-table-cell p-0 cell-vr w-1_25" rowspan="2" v-if="$device.isDesktopOrTablet"></b-td>
    </b-tr>
    <b-tr class="match-table-row" v-if="$device.isMobile">
      <b-th
        class="match-table-cell align-middle font-weight-semibold text-xl" colspan="3">
        Букмекеры РФ:
      </b-th>
    </b-tr>
    <b-tr
      :class="{
        'match-table-row': true,
        'last': $device.isMobile,
      }"
    >
      <b-th class="match-table-cell align-middle font-weight-semibold text-xs text-gray-950 bg-gray-300 rounded-bl-xl" v-if="$device.isDesktopOrTablet">
        Букмекеры России
      </b-th>
      <b-td
        :class="{
          'match-table-cell text-center align-middle bg-gray-200': true,
          'text-lg': $device.isDesktopOrTablet,
          'text-xl': $device.isMobile,
        }"
      >
        1.5
      </b-td>
      <b-td
        :class="{
          'match-table-cell text-center align-middle bg-gray-200': true,
          'text-lg': $device.isDesktopOrTablet,
          'text-3xl': $device.isMobile,
        }"
      >
        1.5
      </b-td>
      <b-td
        :class="{
          'match-table-cell text-center align-middle bg-gray-200': true,
          'text-lg rounded-br-xl': $device.isDesktopOrTablet,
          'text-3xl': $device.isMobile,
        }"
      >
        1.5
      </b-td>
    </b-tr>
    <b-tr class="match-table-row last h-1_25" v-if="$device.isDesktopOrTablet">
      <b-td class="match-table-cell cell-hr p-0" colspan="9"></b-td>
    </b-tr>
  </b-tbody>
</template>

<script>
  import MatchInfo from '@/components/match/match-info';
  import BetFactor from '@/components/bet/bet-factor';

  export default {
    components: {
      MatchInfo,
      BetFactor,
    }
  }
</script>

<style lang="scss">
  .match-table-body {
    .match-table-row.first .match-table-cell {
      &:first-child,
      &:last-child {
        position: relative;
      }

      &:first-child::before,
      &:last-child::after {
        position: absolute;
        content: '';
        width: 10px;
        height: 10px;
        overflow: hidden;
        background-image: url('data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAABQAAAAUCAIAAAAC64paAAAACXBIWXMAAA7EAAAOxAGVKw4bAAAA4UlEQVQ4jaWUQQqCQBSGx6HIhW2cTVOnKLqFIgouXLrwTG7EGwRJ6C1EryAqT4+QKdTCMF0YOvMxy/cx/4P3noAkGY0QdzvT0HRVuV7OR3pACEFVx0kahNHt/ng2DZogycOzbKcEeM9QAli2M67/ynhPXM+f08a4no/3ZCIvNAf/J1u2s9zs+eYXCf3T5xwlgEgoNg3tRClayYlS09CwriprzR5dVVCWF2sz92R5IbzadrvZMPzcdh1my9yDoarZTKhqHCcpmxwnKQ7CiE0OwohrSPjGk3cxeFeS7RgIPGfoA98wLv6WQffcAAAAAElFTkSuQmCC');
      }

      &:first-child::before {
        top: 0;
        left: 0;
        background-position: 0 0;
      }

      &:last-child::after {
        top: 0;
        right: 0;
        background-position: 100% 0;
      }
    }

    .match-table-row.last .match-table-cell {
      &:first-child {
        border-bottom-left-radius: 10px;
      }

      &:last-child {
        border-bottom-right-radius: 10px;
      }
    }

    .match-table-cell.cell-bet {
      background-color: var(--primary);
    }
  }

  .match-table-body-mobile {
    td.match-table-cell {
      padding-top: .625rem;
      padding-bottom: .625rem;

      &.cell-bet {
        padding-top: .875rem;
        padding-bottom: .875rem;
      }
    }

    th.match-table-cell {
      padding-top: .25rem;
      padding-bottom: .25rem;
    }

    .match-table-cell.cell-bet {
      background-color: var(--gray-200);
    }
  }
</style>

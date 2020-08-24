<template>
  <b-table-simple
    table-variant="white"
    borderless
    table-class="match-table-side mb-0"
    responsive=""
  >
    <colgroup>
      <col width="1">
      <col width="33%">
      <col width="33%">
      <col width="33%">
      <col width="1">
    </colgroup>
    <b-thead class="match-table-side-head">
      <b-tr class="match-table-side-row">
        <b-th class="match-table-side-cell bg-white text-gray-950 align-middle cell-match" colspan="5">
          <MatchInfo variant="info-medium" />
        </b-th>
      </b-tr>
      <b-tr class="match-table-side-row">
        <b-td class="match-table-side-cell p-0 cell-vr w-1_25"></b-td>
        <b-th class="match-table-side-cell font-weight-medium text-center text-truncate bg-white text-gray-950 align-bottom text-sm cell-head">Победа 1</b-th>
        <b-th class="match-table-side-cell font-weight-medium text-center text-truncate bg-white text-gray-950 align-bottom text-sm cell-head">Ничья</b-th>
        <b-th class="match-table-side-cell font-weight-medium text-center text-truncate bg-white text-gray-950 align-bottom text-sm cell-head">Победа 2</b-th>
        <b-td class="match-table-side-cell p-0 cell-vr w-1_25"></b-td>
      </b-tr>
    </b-thead>
    <b-tbody class="match-table-side-body">
      <b-tr class="match-table-side-row">
        <b-td class="match-table-side-cell p-0 cell-vr w-1_25" rowspan="4"></b-td>
        <b-th class="match-table-side-cell bg-red-400 rounded-tl-xl"></b-th>
        <b-th class="match-table-side-cell align-middle font-weight-semibold text-lg text-white text-center bg-red-500 rounded-b-xl cell-title">
          Мы нашли
        </b-th>
        <b-th class="match-table-side-cell bg-red-400 rounded-tr-xl"></b-th>
        <b-td class="match-table-side-cell p-0 cell-vr w-1_25" rowspan="4"></b-td>
      </b-tr>
      <b-tr class="match-table-side-row">
        <b-td class="match-table-side-cell cell-bet text-center align-middle bg-red-400">
          <BetFactor factor="1.5" percent="13" outline active column size="large" />
        </b-td>
        <b-td class="match-table-side-cell cell-bet text-center align-middle bg-red-400">
          <BetFactor factor="1.5" percent="13" outline column size="large" />
        </b-td>
        <b-td class="match-table-side-cell cell-bet text-center align-middle bg-red-400">
          <BetFactor factor="1.5" percent="13" outline column size="large" />
        </b-td>
      </b-tr>
      <b-tr class="match-table-side-row">
        <b-th class="match-table-side-cell bg-gray-200"></b-th>
        <b-th class="match-table-side-cell align-middle font-weight-semibold text-xs text-gray-950 bg-gray-300 text-center rounded-b-xl cell-title-2">
          Букмекеры России
        </b-th>
        <b-th class="match-table-side-cel bg-gray-200"></b-th>
      </b-tr>
      <b-tr class="match-table-side-row">
        <b-td class="match-table-side-cell text-center align-middle bg-gray-200 text-sm cell-bet-2 rounded-bl-xl">
          <s>1.5</s>
        </b-td>
        <b-td class="match-table-side-cell text-center align-middle bg-gray-200 text-sm cell-bet-2">
          <s>1.5</s>
        </b-td>
        <b-td class="match-table-side-cell text-center align-middle bg-gray-200 text-sm cell-bet-2 rounded-br-xl">
          <s>1.5</s>
        </b-td>
      </b-tr>
    </b-tbody>
    <b-tfoot class="match-table-side-foot">
      <b-tr class="match-table-side-row">
        <b-td class="match-table-side-cell text-center align-middle font-weight-semibold text-sm text-gray-950 align-middle cell-more" colspan="5">
          <a class="text-gray-950" href="">
            Все коэффициенты
            <svgicon class="text-primary arrow-right w-1_75 h-1_75 ml-1" name="arrow-right" />
          </a>
        </b-td>
      </b-tr>
    </b-tfoot>
  </b-table-simple>
</template>

<script>
  import BetFactor from '@/components/bet/bet-factor';
  import MatchInfo from '@/components/match/match-info';
  import '@/components/icons/arrow-right';

  export default {
    components: {
      MatchInfo,
      BetFactor,
    }
  }
</script>

<style lang="scss">
.match-table-side {
  .match-table-side-cell {
    padding-top: 4px;
    padding-bottom: 4px;

    &.cell-match {
      border-bottom: 1px solid #F2F5F8;
    }
  }

  .match-table-side-cell.cell-hr,
  .match-table-side-cell.cell-vr {
    font-size: 0;
  }

  .match-table-side-cell.cell-vr {
    min-width: .625rem;
  }

  .match-table-side-cell.cell-title,
  .match-table-side-cell.cell-title-2 {
    position: relative;
  }

  .match-table-side-cell.cell-title::before,
  .match-table-side-cell.cell-title::after,
  .match-table-side-cell.cell-title-2::before,
  .match-table-side-cell.cell-title-2::after {
    position: absolute;
    content: '';
    width: 10px;
    height: 10px;
    overflow: hidden;
    background-image: url('data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAABQAAAAUCAIAAAAC64paAAAACXBIWXMAAA7EAAAOxAGVKw4bAAAAxklEQVQ4jZ3UwW6DMBBF0eNRqWAB/fB+bcMCUiTchYGmCmqAu7LludaTrZn0WXkkZyMjEzMIKmpqUvpT/Pa4GbJ+dTZm7tzpabMmPck5uzH4j5kvvrNujRDl4KX5m47buo6S9qC5+UOGyFl/xiz05CzGpxc6wsxIjOfNwkhMV+WJuJC5MG9fdY24bAdRvS7bpyLqq3Jd5AvJo8gpac/LLSkJNElzxmwsjblE7hz1G7p1vfRzSj543xsGG0Frbxgstyb1mTH0A8syObLrikpNAAAAAElFTkSuQmCC');
  }

  .match-table-side-cell.cell-title::before,
  .match-table-side-cell.cell-title::after {
    background-image: url('data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAABQAAAAUCAIAAAAC64paAAAACXBIWXMAAA7EAAAOxAGVKw4bAAAAxklEQVQ4jZ3UwW6DMBBF0eNRqWAB/fB+bcMCUiTchYGmCmqAu7LludaTrZn0WXkkZyMjEzMIKmpqUvpT/Pa4GbJ+dTZm7tzpabMmPck5uzH4j5kvvrNujRDl4KX5m47buo6S9qC5+UOGyFl/xiz05CzGpxc6wsxIjOfNwkhMV+WJuJC5MG9fdY24bAdRvS7bpyLqq3Jd5AvJo8gpac/LLSkJNElzxmwsjblE7hz1G7p1vfRzSj543xsGG0Frbxgstyb1mTH0A8syObLrikpNAAAAAElFTkSuQmCC');
  }

  .match-table-side-cell.cell-title-2::before,
  .match-table-side-cell.cell-title-2::after {
    background-image: url('data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAABQAAAAUCAIAAAAC64paAAAACXBIWXMAAA7EAAAOxAGVKw4bAAAA3ElEQVQ4jZ2USw6DMAwF8xybT+9/zK66KFA7cheuooi2IjArIjzWU8DG/bGkBndXNVMrVtw9pQQgc2ZhEQbQFnN70JeuyxZO287UTG0DpnmUQfayu6/Lpi9N/3H35bmalWkeIwLFi0Nzly6eKc6dZvWjniJwv1mTujup2u6GeoiPQqZ21gxMjYqVa3KxQhcyB+5O18yAdn9cPwAoc74mZ87EwseFv2Bh+p6VHgCIMAGY5vGsHLNBKSUZpB20Q2o91U6dvgxSk35uC8B8m5jz9zKo4N8yqF1ZuH8NvQEGOIsAY7p9YAAAAABJRU5ErkJggg==');
  }

  .match-table-side-cell.cell-title::before,
  .match-table-side-cell.cell-title-2::before {
    bottom: 0;
    left: 0;
    background-position: 0 100%;
  }

  .match-table-side-cell.cell-title::after,
  .match-table-side-cell.cell-title-2::after {
    bottom: 0;
    right: 0;
    background-position: 100% 100%;
  }

  .match-table-side-cell.cell-match { height: 86px; }
  .match-table-side-cell.cell-head { height: 42px; }
  .match-table-side-cell.cell-title { height: 34px; }
  .match-table-side-cell.cell-title-2 { height: 34px; }
  .match-table-side-cell.cell-bet { padding: 12px 4px; }
  .match-table-side-cell.cell-bet:first-child { padding-left: 8px; }
  .match-table-side-cell.cell-bet:last-child { padding-right: 8px; }
  .match-table-side-cell.cell-bet-2 { height: 40px; }
  .match-table-side-cell.cell-more { height: 45px; }
}
</style>

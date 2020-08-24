<template>
  <b-card tag="section" class="side-bet-card border-0 mb-2" no-body bg-variant="transparent">
    <b-card-header
      header-tag="header"
      header-bg-variant="dark"
      header-text-variant="white"
      class="side-bet-card-header d-flex align-items-center"
    >
      <svgicon class="w-3 h-3 mr-1_75 flex-shrink-0" name="doc" />
      <span class="flex-grow-1 text-truncate">
        Новое пари
      </span>
    </b-card-header>
    <div class="card-table-head text-xs bg-dark">
      <div class="row card-table-row no-gutters">
        <div class="card-table-cell col-6 py-0_75 pl-2_5 pr-0_75">Событие</div>
        <div class="card-table-cell col-3 py-0_75 px-0_75">Исход</div>
        <div class="card-table-cell col-3 py-0_75 pl-0_75 pr-2_5">Коэф.</div>
      </div>
    </div>
    <b-alert show variant="success" class="text-center py-2_75 mb-0 card-alert rounded-t-0 rounded-t-0">
      <h5 class="h5 mb-0 d-inline-flex flex-nowrap leading-5 text-left">
        <svgicon class="w-2_25 h-2_25 flex-shrink-0 mr-1 svg-stroke text-green" name="check" />
        Ставка успешно принята
      </h5>
    </b-alert>
  </b-card>
</template>

<script>
  import '@/components/icons/doc';
  import '@/components/icons/check';

  export default {
  }
</script>

<style lang="scss">
  .side-bet-card {}
</style>

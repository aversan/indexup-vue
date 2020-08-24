<template>
  <div class="mx-n2_5" v-if="$device.isMobile">
    <nav class="main-menu main-menu-mobile">
      <div class="overflow-hidden mw-100 h-9_5">
        <b-nav pills class="flex-nowrap mb-0 pb-4 overflow-x-auto scrolling-touch text-nowrap justify-content-between px-2_5">
          <b-nav-item class="py-1" link-classes="px-2 py-1_5 text-3xl font-weight-medium" active>Главная</b-nav-item>
          <b-nav-item class="py-1" link-classes="px-2 py-1_5 text-3xl font-weight-medium"><span class="svg-icon svg-icon-online w-2 h-2 mr-1_5"></span>Live</b-nav-item>
          <b-nav-item class="py-1" link-classes="px-2 py-1_5 text-3xl font-weight-medium">Линия</b-nav-item>
          <b-nav-item class="py-1" link-classes="px-2 py-1_5 text-3xl font-weight-medium">О Index</b-nav-item>
          <b-nav-item class="py-1" link-classes="px-2 py-1_5 text-3xl font-weight-medium">Правила</b-nav-item>
        </b-nav>
      </div>
    </nav>
  </div>
</template>

<script>
  export default {
    data() {
      return {
      }
    },
    components: {
    },
  }
</script>

<style lang="scss">
  .main-menu-mobile {
    &.main-menu {
      border-top: 1px solid var(--gray-975);
      border-bottom: 1px solid var(--gray-975);
    }
  }
</style>

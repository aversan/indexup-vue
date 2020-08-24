<template>
  <b-card-header
    header-bg-variant="dark"
    header-text-variant="white"
    :class="{
      'match-group-header d-flex flex-nowrap align-items-center p-0': true,
      'h-10_25 rounded-xl': $device.isDesktopOrTablet,
      'h-8_25': $device.isMobile,
    }"
  >
    <span
      :class="{
          'match-group-header-icon-wrapper d-flex align-items-center justify-content-center rounded-xl flex-shrink-0': true,
          'h-10_25 w-10_25 mr-3_5': $device.isDesktopOrTablet,
          'h-6_75 w-6_75 ml-0_75 mr-2_5': $device.isMobile,
          ['bg-' + icon]: icon,
        }"
    >
      <svgicon
        :class="{
          'match-group-header-icon': true,
          'h-4 w-4': $device.isDesktopOrTablet,
          'h-3_25 w-3_25': $device.isMobile,
        }"
        :name="icon"
      />
    </span>
    <h3
      :class="{
          'match-group-header-title mb-0 flex-grow-1 text-truncate': true,
          'h3': $device.isDesktopOrTablet,
          'h2': $device.isMobile,
        }"
    >
      {{ title }}
    </h3>
    <div
      class="match-group-header-secondary overflow-hidden h-10_25"
    >
      <b-nav class="nav nav-tabs card-header-tabs text-sm flex-nowrap mb-0 pb-4 overflow-x-auto scrolling-touch text-nowrap" v-if="$device.isDesktopOrTablet">
        <b-nav-item link-classes="px-3 py-1_5 h-10_25 d-flex align-items-center justify-content-center" v-for="item in items" :key="item.text" :href="item.url" :active="item.isActive">{{ item.text }}</b-nav-item>
      </b-nav>
    </div>
    <b-dropdown variant="link" menu-class="py-2_5 dropdown-mobile" toggle-class="h-6_75 px-2_5 text-decoration-none text-xl font-weight-light" no-caret right v-if="$device.isMobile">
      <template v-slot:button-content>
        Исходы
        <svgicon class="h-2_5 w-2_5 ml-2 text-primary" name="chevron-down" />
      </template>
      <b-dropdown-item link-class="text-xl font-weight-light px-3_75 py-1" v-for="item in items" :key="item.text" :href="item.url" :active="item.isActive">{{ item.text }}</b-dropdown-item>
    </b-dropdown>
  </b-card-header>
</template>

<script>
  import '@/components/shared/sport-icons';
  import '@/components/icons/chevron-down';

  export default {
    data() {
      return {
        items: [
          { text: "Исходы", url: "#", isActive: true },
          { text: "Двойные шансы", url: "#" },
          { text: "Тоталы", url: "#" },
          { text: "Форы", url: "#" },
        ],
      }
    },
    components: {
    },
    props: {
      title: {
        type: String,
        default: '',
      },
      icon: {
        type: String,
        default: 'football',
      },
    },
  }
</script>

<style lang="scss">
  .match-group-header {}
</style>

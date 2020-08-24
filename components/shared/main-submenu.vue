<template>
  <div
    :class="{
      'mx-n2_5': true,
      'mx-xl-0 rounded-xl bg-dark my-1_5': $device.isDesktopOrTablet,
    }"
  >
    <nav
      :class="{
          'main-submenu': true,
          'main-submenu-mobile': $device.isMobile,
        }"
    >
      <div
        :class="{
          'overflow-hidden mw-100': true,
          'h-6_25': $device.isDesktopOrTablet,
          'h-9_5': $device.isMobile,
        }"
      >
        <b-nav
          :pills="$device.isDesktopOrTablet"
          :class="{
            'flex-nowrap mb-0 pb-4 overflow-x-auto scrolling-touch text-nowrap': true,
            'justify-content-between px-0_75': $device.isMobile,
            'px-2_5 px-xl-0_75': $device.isDesktopOrTablet,
          }"
        >
          <b-nav-item v-if="$device.isDesktopOrTablet" class="py-0_75" link-classes="px-3_5 py-1 text-sm-2 font-weight-semibold" v-for="item in items" :key="item.text" :href="item.url" :active="item.isActive">{{ item.text }}</b-nav-item>
          <b-nav-item v-if="$device.isMobile" class="pt-1" link-classes="px-3_75 py-2 text-3xl font-weight-medium" v-for="item in items" :key="item.text" :href="item.url" :active="item.isActive">{{ item.text }}</b-nav-item>
        </b-nav>
      </div>
    </nav>
  </div>
</template>

<script>
  export default {
    data() {
      return {
        items: [
          { text: "Главная", url: "#", isActive: true },
          { text: "Фора", url: "#" },
          { text: "Тоталы", url: "#" },
          { text: "Голы", url: "#" },
        ],
      }
    },
    components: {
    },
  }
</script>

<style lang="scss">
  .main-submenu-mobile {
    &.main-submenu {
      border-bottom: 1px solid var(--gray-975);
    }

    .nav-link {
      position: relative;
      color: var(--muted);
    }

    .nav-link:hover,
    .nav-link:focus {
      color: var(--white);
    }

    .nav-link.active,
    .nav-link.active:hover,
    .nav-link.active:focus {
      color: var(--white);
    }

    .nav-link.active::before {
      content: '';
      height: .375rem;
      border-radius: 1rem;
      background-image: linear-gradient(41.95deg, #EE2B31 6.44%, #9E1215 87.71%);
      position: absolute;
      bottom: 0;
      left: 1rem;
      right: 1rem;
    }
  }
</style>

<template>
  <div
    :class="{
      'bet-factor d-inline-flex flex-nowrap rounded-xl text-nowrap': true,
      'align-self-stretch': $device.isDesktopOrTablet,
      'bet-factor-mobile': $device.isMobile,
      'border border-white-20': $device.isDesktopOrTablet && outline,
      'flex-column p-1': column,
      'bg-primary': $device.isDesktopOrTablet && !active,
      'bg-red-300 border-red-300': $device.isDesktopOrTablet && active,
      'bg-transparent': $device.isMobile && !active,
      'bg-transparent': $device.isMobile && active,
    }"
  >
    <div
      :class="{
        'flex-grow-1 bet-factor-primary d-flex align-items-center': true,
        'justify-content-center': column,
        'px-1_75': $device.isDesktopOrTablet && size == 'small',
        'px-1': $device.isDesktopOrTablet && size == 'medium',
        '': $device.isDesktopOrTablet && size == 'large',
        'flex-column justify-content-center': $device.isMobile,
        // '': $device.isMobile && size == 'small',
        // '': $device.isMobile && size == 'medium',
        // '': $device.isMobile && size == 'large',
      }"
    >
      <strong
        :class="{
          'font-weight-normal': true,
          'text-white': $device.isDesktopOrTablet,
          'text-gray-900': $device.isMobile,
          'text-lg px-0_75 py-1_25': $device.isDesktopOrTablet && size == 'small',
          'text-xl px-1 py-1_25': $device.isDesktopOrTablet && size == 'medium',
          // 'text-7xl px-2 py-1_5': $device.isDesktopOrTablet && size == 'large',
          'text-3xl px-0_75 py-0': $device.isMobile && size == 'small',
          'text-5xl px-1 py-0': $device.isMobile && size == 'medium',
          // 'text-7xl px-2 py-1_5': $device.isMobile && size == 'large',
          'text-7xl px-2 py-1_5': size == 'large',
        }"
      >
        {{ factor }}
        <svgicon
          :class="{
            'w-1_25 h-1_25': $device.isDesktopOrTablet && size == 'small',
            'w-2 h-2': $device.isDesktopOrTablet && size == 'medium',
            // 'w-3 h-3': $device.isDesktopOrTablet && size == 'large',
            'w-1_5 h-1_5': $device.isMobile && size == 'small',
            'w-2_5 h-2_5': $device.isMobile && size == 'medium',
            // 'w-3 h-3': $device.isMobile && size == 'large',
            'w-3 h-3': size == 'large',
          }"
          name="up"
        />
      </strong>
      <s
        :class="{
          'font-weight-normal': true,
          'text-pink': $device.isDesktopOrTablet,
          'text-muted': $device.isMobile,
          'text-base px-0_75 py-1_25': $device.isDesktopOrTablet && size == 'small',
          'text-lg px-1 py-1_25': $device.isDesktopOrTablet && size == 'medium',
          // 'text-6xl px-1 py-1_25': $device.isDesktopOrTablet && size == 'large',
          'text-lg px-0_75 py-0 mt-0_5': $device.isMobile && size == 'small',
          'text-2xl px-1 py-0 mt-0_5': $device.isMobile && size == 'medium',
          // 'text-6xl px-1 py-1_25': $device.isMobile && size == 'large',
          'text-6xl px-1 py-1_25': size == 'large',
        }"
        v-if="!!oldFactor"
      >
        {{ factor }}
      </s>
    </div>
    <small
      id="tooltip-target-1"
      :class="{
        'd-flex flex-column font-weight-bold bet-factor-secondary bg-gray-900 text-white rounded-xl text-center justify-content-center overflow-hidden': true,
        'text-xs px-1_5 py-0_5': $device.isDesktopOrTablet && size == 'small',
        'text-sm px-1_25 py-0_5': $device.isDesktopOrTablet && size == 'medium',
        // 'text-lg px-1_5 py-1_25': $device.isDesktopOrTablet && size == 'large',
        'text-base px-1_5 py-1_75': $device.isMobile && size == 'small',
        'text-xl px-2 py-1_75': $device.isMobile && size == 'medium',
        // 'text-lg px-1_5 py-1_25': $device.isMobile && size == 'large',
        'text-base px-1_5 py-1_25': size == 'large',
      }"
    >
      <span>+{{ percent }}%</span>
      <span
        :class="{
          'sr-only': $device.isMobile,
        }"
      >
        к выиграшу
      </span>
    </small>
    <b-tooltip custom-class="bet-factor-tooltip" target="tooltip-target-1" placement="bottom" triggers="hover">
      Мы нашли самые высокие коэффициенты на ближайшие ТОП-матчи!
    </b-tooltip>
  </div>
</template>

<script>
  import '@/components/icons/up';

  export default {
    components: {
    },
    props: {
      factor: {
        type: String,
        default: "1.5",
      },
      oldFactor: {
        type: String,
        default: "",
      },
      percent: {
        type: String,
        default: "13",
      },
      outline: {
        type: Boolean,
        default: false,
      },
      active: {
        type: Boolean,
        default: false,
      },
      size: {
        type: String,
        default: 'medium', // large medium small
      },
      column: {
        type: Boolean,
        default: false,
      },
    },
  }
</script>

<style lang="scss">
  .bet-factor {
    line-height: 1.25rem;

    &.flex-column {
      max-width: 130px;
    }

    .bet-factor-secondary {
      box-shadow: 0 7px 15px rgba(93, 6, 3, .4);
    }

    &.active {
      box-shadow: 0 10px 20px rgba(93, 6, 3, 0.6);
    }
  }

  .bet-factor-mobile {
    .bet-factor-secondary {
      box-shadow: 0 14px 30px rgba(93, 6, 3, .4);
    }
  }


  .bet-factor-tooltip {
    .tooltip-inner {
      text-align: left;
      /*transform: translateY(20px);*/
    }
  }
</style>

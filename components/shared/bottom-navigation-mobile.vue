<template>
  <div class="bottom-navigation-holder h-13_25 bottom-navigation-mobile" v-if="$device.isMobile">
    <nav class="bottom-navigation bottom-navigation-mobile fixed-bottom w-100 bg-black">
      <div class="mw-100 h-13_25">
        <ul class="list-unstyled row no-gutters mb-0 pb-4 bottom-navigation-list justify-content-between">
          <li class="bottom-navigation-item position-relative col" v-for="item in items" :key="item.icon">
            <a class="d-flex flex-column text-center px-2 pt-2_5 bottom-navigation-link h-13_25"  :class="'is-' + item.icon" :href="item.url">
              <span class="w-9_5 h-9_5 rounded-xl d-flex align-items-center justify-content-center bottom-navigation-icon-wrapper position-absolute" :class="'is-' + item.icon"></span>
              <svgicon class="w-5 h-5 bottom-navigation-icon mx-auto" :class="'is-' + item.icon" :name="item.icon" />
              <span class="text-truncate text-xl bottom-navigation-text" :class="'is-' + item.icon">{{ item.text }}</span>
            </a>
          </li>
        </ul>
      </div>
    </nav>
  </div>
</template>

<script>
  import '@/components/icons/phone';
  import '@/components/icons/live';
  import '@/components/icons/coupon';
  import '@/components/icons/line';
  import '@/components/icons/account';

  export default {
    data() {
      return {
        items: [
          { icon: "phone", text: "Главная", url: "" },
          { icon: "live", text: "Live", url: "" },
          { icon: "coupon", text: "Купон", url: "" },
          { icon: "line", text: "Линия", url: "" },
          { icon: "account", text: "Аккаунт", url: "" },
        ],
      }
    },
    components: {
    },
  }
</script>

<style lang="scss">
  .bottom-navigation-mobile {
    &.bottom-navigation {
      border-top: 1px solid var(--gray-975);
    }

    .bottom-navigation-link.active {
      position: relative;
    }

    .bottom-navigation-link.active::before {
      content: '';
      height: .375rem;
      border-radius: 1rem;
      background-image: linear-gradient(41.95deg, #EE2B31 6.44%, #9E1215 87.71%);
      position: absolute;
      top: -.1875rem;
      left: 1rem;
      right: 1rem;
    }

    .bottom-navigation-icon-wrapper {
      left: 50%;
      top: 50%;
      transform: translate(-50%, -50%);
      z-index: -1;
    }

    .bottom-navigation-icon-wrapper.is-coupon {
      background: var(--button-gradient-red);
      box-shadow: 0 0 30px rgba(201, 32, 36, 0.8);
      margin-top: -.625rem;
      top: calc(50% + .75rem);
    }

    .bottom-navigation-link.active .bottom-navigation-icon-wrapper.is-coupon,
    .bottom-navigation-link.active:hover .bottom-navigation-icon-wrapper.is-coupon,
    .bottom-navigation-link.active:focus .bottom-navigation-icon-wrapper.is-coupon {
      background: var(--white);
      box-shadow: none;
    }

    .bottom-navigation-icon {
      color: var(--white);

      &.is-coupon {
        position: relative;
        top: .75rem;
      }
    }

    .bottom-navigation-link.active .bottom-navigation-icon.is-coupon,
    .bottom-navigation-link.active:hover .bottom-navigation-icon.is-coupon,
    .bottom-navigation-link.active:focus .bottom-navigation-icon.is-coupon {
      color: #EE2B31;
    }

    .bottom-navigation-text {
      line-height: 2.5rem;
      color: var(--muted);

      &.is-coupon {
        position: absolute;
        width: 1px;
        height: 1px;
        padding: 0;
        margin: -1px;
        overflow: hidden;
        clip: rect(0, 0, 0, 0);
        white-space: nowrap;
        border: 0;
      }
    }

    .bottom-navigation-link.active .bottom-navigation-text,
    .bottom-navigation-link.active:hover .bottom-navigation-text,
    .bottom-navigation-link.active:focus .bottom-navigation-text {
      color: var(--white);
    }
  }
</style>

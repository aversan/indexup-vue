<template>
  <div>
    <nav class="main-super-top d-flex align-items-end" v-if="$device.isDesktopOrTablet">
      <h6 class="h6 mb-0 text-sm-2 text-nowrap mr-3 d-flex align-items-center flex-nowrap">
        <svgicon class="w-3 h-3 text-primary mr-0_25" name="hot" />
        Супертоп
      </h6>
      <ul class="list-unstyled list-inline m-n1_75 mb-0">
        <li class="list-inline-item m-1_75 main-super-top-item" v-for="category in categories" :key="category.key">
          <a class="main-super-top-link" :href="category.url" :title="category.text">
            <svgicon class="w-3 h-3 main-super-top-icon" :name="category.key" />
            <span class="sr-only main-super-top-text">{{ category.text }}</span>
          </a>
        </li>
      </ul>
    </nav>
    <div class="mx-n2_5" v-if="$device.isMobile">
      <nav class="main-super-top main-super-top-mobile d-flex">
        <h6 class="mb-0 font-weight-normal mw-12_5 pl-0_5">
          <span class="d-flex flex-column text-center pt-2_25 px-2">
            <span class="w-6_5 h-6_5 rounded-xl d-flex align-items-center justify-content-center mx-auto">
              <svgicon class="w-3_5 h-3_5 text-primary" name="hot" />
            </span>
            <span class="text-truncate text-gray-300 text-lg main-super-top-title">Супертоп</span>
          </span>
        </h6>
        <div class="overflow-hidden mw-100 h-13_75 pr-0_5">
          <ul class="list-unstyled d-flex align-items-end flex-nowrap mb-0 pb-4 overflow-x-auto scrolling-touch text-nowrap">
            <li class="main-super-top-item mw-12_5" v-for="category in categories" :key="category.key">
              <a class="d-flex flex-column text-center pt-2_25 px-2 main-super-top-link" :href="category.url" :title="category.text">
                <span class="w-6_5 h-6_5 rounded-xl d-flex align-items-center justify-content-center mx-auto main-super-top-icon-wrapper">
                  <svgicon class="w-3_5 h-3_5 main-super-top-icon" :name="category.key" />
                </span>
                <span class="text-truncate text-gray-300 text-xl main-super-top-text">{{ category.text }}</span>
              </a>
            </li>
          </ul>
        </div>
      </nav>
    </div>
  </div>
</template>

<script>
  import '@/components/icons/hot';
  import '@/components/shared/sport-icons';

  export default {
    data() {
      return {
        categories: [
          { key: "tennis", text: "Теннис", url: "" },
          { key: "football", text: "Футбол", url: "" },
          { key: "e-sports", text: "Киберспорт", url: "" },
          { key: "hockey", text: "Хоккей", url: "" },
          { key: "volleyball", text: "Волейбол", url: "" },
          { key: "moto", text: "Авто-мотоспорт", url: "" },
          { key: "badminton", text: "Бадминтон", url: "" },
          { key: "mma", text: "MMA", url: "" },
          { key: "rugby", text: "Регби", url: "" },
        ],
      }
    },
    components: {
    },
  }
</script>

<style lang="scss">
  .main-super-top {
    .main-super-top-icon {
      color: var(--muted);
    }

    .main-super-top-link:hover .main-super-top-icon,
    .main-super-top-link:focus .main-super-top-icon {
      color: var(--white);
    }

    .main-super-top-link.active .main-super-top-icon,
    .main-super-top-link.active:hover .main-super-top-icon,
    .main-super-top-link.active:focus .main-super-top-icon {
      color: var(--white);
    }
  }

  .main-super-top-mobile {
    .main-super-top-title,
    .main-super-top-text {
      line-height: 2.5rem;
    }

    .main-super-top-link.active .main-super-top-icon-wrapper,
    .main-super-top-link.active:hover .main-super-top-icon-wrapper,
    .main-super-top-link.active:focus .main-super-top-icon-wrapper {
      background: var(--button-gradient-red);
    }

    .main-super-top-icon {
      color: var(--gray-600);
    }

    .main-super-top-link:hover .main-super-top-icon,
    .main-super-top-link:focus .main-super-top-icon {
      color: var(--white);
    }

    .main-super-top-link.active .main-super-top-icon,
    .main-super-top-link.active:hover .main-super-top-icon,
    .main-super-top-link.active:focus .main-super-top-icon {
      color: var(--white);
    }
  }
</style>

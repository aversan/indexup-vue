<template>
  <b-card tag="nav" no-body bg-variant="secondary" class="main-category-navigation px-0 px-md-3_75 px-xl-7_5 py-2_5 py-xl-5 mt-0 mb-2 my-xl-5" v-if="$device.isDesktopOrTablet">
    <b-list-group class="list-group list-group-flush main-category-list d-block">
      <b-list-group-item class="d-flex align-items-center position-relative bg-gray-150 h-8 main-category-item" v-for="category in categories" :key="category.key" :href="'#' + category.key">
        <svgicon class="text-gray-975 w-3_25 h-3_25 mr-2_5 ml-0_75 flex-shrink-0" :name="category.key" />
        <span class="flex-grow-1 mw-100 text-truncate">
          <span class="text-gray-950">
            {{ category.text }}
          </span>
        </span>
        <span class="bg-gray-250 rounded-pill w-4 h-4 flex-shrink-0 d-flex align-items-center justify-content-center ml-2_5">
          <svgicon class="w-1 h-1 text-primary" name="chevron-down" />
        </span>
      </b-list-group-item>
    </b-list-group>
  </b-card>
</template>

<script>
  import '@/components/icons/chevron-down';
  import '@/components/shared/sport-icons';

  export default {
    data() {
      return {
        categories: [
          { key: "football", text: "Футбол" },
          { key: "hockey", text: "Хоккей" },
          { key: "tennis", text: "Теннис" },
          { key: "e-sports", text: "Киберспорт" },
          { key: "rugby", text: "Регби" },

          { key: "ufc", text: "UFC" },
          { key: "basketball", text: "Баскетбол" },
          { key: "volleyball", text: "Волейбол" },
          { key: "table-tennis", text: "Настольный теннис" },
          { key: "handball", text: "Гандбол" },

          { key: "moto", text: "Авто-мотоспорт" },
          { key: "american-football", text: "Американский футбол" },
          { key: "badminton", text: "Бадминтон" },
          { key: "baseball", text: "Бейсбол" },
          { key: "biathlon", text: "Биатлон" },

          { key: "billiards", text: "Бильярд" },
          { key: "boxing", text: "Бокс" },
          { key: "water-polo", text: "Водное поло" },
          { key: "darts", text: "Дартс" },
          { key: "mma", text: "MMA" },
        ],
      }
    },
    components: {
    },
  }
</script>

<style lang="scss">
  .main-category-navigation {
    .main-category-list {
      column-count: 4;
      column-gap: 1.875rem;

      @media (max-width: 1200px) {
        column-count: 2;
      }
    }

    .main-category-item {
      break-inside: avoid-column;
    }
  }
</style>

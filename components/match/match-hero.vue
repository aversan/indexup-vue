   <template>
  <b-card
    tag="div"
    text-variant="white"
    :class="{
      'match-hero overflow-hidden': true,
      'my-1_5': $device.isDesktopOrTablet,
      'match-hero-mobile embed-responsive my-3': $device.isMobile,
    }"
    no-body
  >
    <picture class="w-100 h-100">
      <source :srcset="image" type="image/jpg" v-if="$device.isDesktopOrTablet">
      <source :srcset="imageMobile" type="image/jpg" v-if="$device.isMobile">
      <b-card-img
        loading="lazy"
        :class="{
          'match-hero-image': true,
          'embed-responsive-item': $device.isMobile,
        }"
        :src="image"
        alt=""
        class=" cover-object"></b-card-img>
    </picture>
    <b-card-body class="match-hero-body d-flex align-items-center justify-content-center" overlay>
      <MatchInfo />
    </b-card-body>
  </b-card>
</template>

<script>
  import MatchInfo from '@/components/match/match-info';

  export default {
    data() {
      return {
        image: "/images/match-hero-01-desktop.jpg",
        imageMobile: "/images/match-hero-01-mobile.jpg",
        url: "#",
      }
    },
    components: {
      MatchInfo,
    },
  }
</script>

<style lang="scss">
  .match-hero {
    height: 11.25rem;

    .match-info-secondary {
      max-width: 13.75rem;
    }
  }

  .match-hero-mobile {
    height: auto;
    max-height: 18.75rem; // 300px

    &::before {
      padding-top: percentage(260 / 600);
    }

    .match-info-secondary {
      max-width: 8.75rem;
    }
  }
</style>

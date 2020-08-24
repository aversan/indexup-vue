<template>
  <div class="min-vh-100 d-flex flex-column">
    <div class="flex-grow-1">
      <Header />
      <main>
        <b-container fluid="">
          <MainTopAlert />
          <MainSlider />
          <MainMenuMobile />
          <MainCategoryNavigation />
          <b-row>
            <b-col
              cols="12"
              lg="8"
              xl="9"
              :class="{
                'col-main': $device.isDesktopOrTablet,
              }"
            >
              <div class="d-flex align-items-xl-end justify-content-xl-between flex-column flex-xl-row flex-xl-nowrap">
                <MainBreadcrumb class="mb-2" />
                <MainSuperTop class="mb-2" />
              </div>
              <MainMainAlert />
              <div>
                <b-card class="match-group-section bg-transparent" no-body v-for="group in matchGroup" :key="group.icon">
                  <MatchGroupHeader :icon="group.icon" :title="group.title"  />
                  <MatchTable />
                </b-card>
              </div>
            </b-col>
            <b-col tag="aside" class="col-side d-none d-xl-block" cols="12" lg="4" xl="3" v-if="$device.isDesktopOrTablet">
              <SideBetCard />
              <SideBanner image="/images/side-banner-01-desktop.jpg" url="#" alt=""  />
              <MatchForecastSide />
              <SideBanner image="/images/side-banner-02-desktop.jpg" url="#" alt=""  />
            </b-col>
          </b-row>
        </b-container>
      </main>
    </div>
    <Footer />
    <BottomNavigationMobile />
  </div>
</template>

<script>
  import MainTopAlert from '@/components/main/main-top-alert';
  import MainSlider from '@/components/main/main-slider';
  import MainCategoryNavigation from '@/components/main/main-category-navigation';
  import MainBreadcrumb from '@/components/shared/main-breadcrumb';
  import MainSuperTop from '@/components/main/main-super-top';
  import MainMainAlert from '@/components/main/main-main-alert';
  import Header from '@/components/shared/header';
  import Footer from '@/components/shared/footer';
  import BottomNavigationMobile from '@/components/shared/bottom-navigation-mobile';
  import MainMenuMobile from '@/components/shared/main-menu-mobile';
  import SideBanner from '@/components/shared/side-banner';
  import SideBetCard from '@/components/shared/side-bet-card';
  import MatchGroupHeader from '@/components/match/match-group-header';
  import MatchTable from '@/components/match/match-table';
  import MatchForecastSide from '@/components/match/match-forecast-side';


  export default {
    loading: true,
    data() {
      return {
        matchGroup: [
          { icon: "tennis", title: "Теннис" },
          { icon: "football", title: "Футбол" },
        ],
      }
    },
    components: {
      Header,
      MainTopAlert,
      MainSlider,
      MainMenuMobile,
      MainCategoryNavigation,
      MainBreadcrumb,
      MainSuperTop,
      MainMainAlert,
      Footer,
      BottomNavigationMobile,
      SideBanner,
      SideBetCard,
      MatchGroupHeader,
      MatchTable,
      MatchForecastSide,
    },
  }
</script>

<style lang="scss">
</style>

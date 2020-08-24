<template>
  <div class="min-vh-100 d-flex flex-column">
    <div class="flex-grow-1">
      <Header />
      <main>
        <b-container fluid="">
          <b-row>
            <b-col
              cols="12"
              lg="8"
              xl="9"
              :class="{
                'col-main': $device.isDesktopOrTablet,
              }"
            >
              <MainBreadcrumb class="my-2" />
              <MatchHero />
              <MainMenuMobile />
              <MainSubmenu />
              <MatchForecastMain />
              <MatchForecast />
            </b-col>
            <b-col cols="12" lg="4" xl="3" tag="aside" class="col-side d-none d-xl-block" v-if="$device.isDesktopOrTablet">
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
  import MainBreadcrumb from '@/components/shared/main-breadcrumb';
  import MatchHero from '@/components/match/match-hero';
  import MatchForecastMain from '@/components/match/match-forecast-main';
  import MatchForecast from '@/components/match/match-forecast';
  import Header from '@/components/shared/header';
  import Footer from '@/components/shared/footer';
  import BottomNavigationMobile from '@/components/shared/bottom-navigation-mobile';
  import MainMenuMobile from '@/components/shared/main-menu-mobile';
  import MainSubmenu from '@/components/shared/main-submenu';
  import SideBanner from '@/components/shared/side-banner';
  import MatchForecastSide from '@/components/match/match-forecast-side'

  export default {
    components: {
      MatchForecastSide,
      Header,
      MatchHero,
      MainMenuMobile,
      MatchForecastMain,
      MatchForecast,
      MainSubmenu,
      MainBreadcrumb,
      Footer,
      BottomNavigationMobile,
      SideBanner,
    }
  }
</script>

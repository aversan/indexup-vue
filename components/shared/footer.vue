<template>
  <footer
    :class="{
      'pt-5_75 pb-3_25 border-top border-white-04': $device.isDesktopOrTablet,
      'py-2_5': $device.isMobile,
    }"
  >
      <b-container fluid>
      <b-row>
        <b-col class="d-flex flex-column justify-content-end justify-content-xl-start" cols="6" xl="3" order="3" order-xl="1">
          <a class="d-none d-xl-block" href="" v-if="$device.isDesktopOrTablet">
            <IndexUpLogo class="footer-logo mt-1" />
            <span class="sr-only">IndexUp</span>
          </a>
          <div
            class=""
            :class="{
              'd-flex align-items-center flex-nowrap mt-2_5 mt-xl-4_25 mb-2_5 mb-xl-0': true,
              '': $device.isDesktopOrTablet,
              'justify-content-end': $device.isMobile,
            }"
          >
            <span class="text-muted mr-2 d-none d-xl-block" v-if="$device.isDesktopOrTablet">Приложение</span>
            <AndroidButton class="header-button mr-0_5" />
            <IOSButton class="header-button mr-0_5" />
          </div>
        </b-col>
        <b-col cols="12" xl="6" order="1" order-xl="2">
          <b-row cols="2" cols-xl="4" v-if="$device.isDesktopOrTablet">
            <b-col>
              <nav>
                <h5 class="h5 footer-title mb-0">Помощь</h5>
                <ul class="list-unstyled text-sm footer-list py-1_25 mb-0">
                  <li class="my-1_25"><a class="text-danger underline" href="">Ваша первая ставка</a></li>
                  <li class="my-1_25" v-for="item in service" :key="item.text">
                    <a class="text-muted" :href="item.url">
                      {{ item.text }}
                    </a>
                  </li>
                </ul>
              </nav>
            </b-col>
            <b-col>
              <nav>
                <h5 class="h5 footer-title mb-0">Сервисы</h5>
                <ul class="list-unstyled text-sm footer-list py-1_25 mb-0">
                  <li class="my-1_25" v-for="item in service" :key="item.text">
                    <a class="text-muted" :href="item.url">
                      {{ item.text }}
                    </a>
                  </li>
                </ul>
              </nav>
            </b-col>
            <b-col>
              <nav>
                <h5 class="h5 footer-title mb-0">Index</h5>
                <ul class="list-unstyled text-sm footer-list py-1_25 mb-0">
                  <li class="my-1_25" v-for="item in index" :key="item.text">
                    <a class="text-muted" :href="item.url">
                      {{ item.text }}
                    </a>
                  </li>
                </ul>
              </nav>
            </b-col>
            <b-col>
              <nav>
                <h5 class="h5 footer-title mb-0">Личный кабинет</h5>
                <ul class="list-unstyled text-sm foonter-list py-1_25 mb-0">
                  <li class="my-1_25" v-for="item in cabinet" :key="item.text">
                    <a class="text-muted" :href="item.url">
                      {{ item.text }}
                    </a>
                  </li>
                </ul>
              </nav>
            </b-col>
          </b-row>
          <b-row class="justify-content-between" v-if="$device.isMobile">
            <b-col cols="5">
              <nav>
                <ul class="list-unstyled text-xl footer-list pb-0 mb-0">
                  <li class="my-2_5">
                    <a class="text-white" href="">
                      Партнерская программа
                    </a>
                  </li>
                  <li class="my-2_5">
                    <a class="text-white" href="">
                      Правила
                    </a>
                  </li>
                </ul>
              </nav>
            </b-col>
            <b-col cols="5">
              <nav>
                <ul class="list-unstyled text-xl footer-list mb-0">
                  <li class="my-2_5">
                    <a class="text-white" href="">
                      <svgicon class="text-blue w-2_5 h-2_5 mr-2" name="lock" />
                      Доступ к сайту
                    </a>
                  </li>
                  <li class="my-2_5">
                    <a class="text-white" href="">
                      Бонусы и акции
                    </a>
                  </li>
                </ul>
              </nav>
            </b-col>
          </b-row>
        </b-col>
        <b-col class="d-xl-flex" cols="6" xl="3" order="1" order-xl="3">
          <nav class="ml-xl-auto">
            <h5 class="h5 footer-title mt-2_5 mt-xl-0 mb-0" v-if="$device.isDesktopOrTablet">Социальные сети</h5>
            <ul class="list-unstyled text-sm footer-social-list py-1_25 mx-n0_25 mb-0 text-nowrap">
              <li class="list-inline-item my-1_25 mx-0_25 footer-social-item" v-for="item in social" :key="item.key">
                <a class="btn h-6 w-6 d-inline-flex align-items-center justify-content-center btn-social rounded-pill" :href="item.url" :title="item.text" target="_blank">
                  <svgicon
                    :class="{
                      'h-2_25 w-2_25': $device.isDesktopOrTablet,
                      'h-2_5 w-2_5': $device.isMobile
                    }"
                    :name="item.key"
                  />
                  <span class="sr-only">{{ item.text }}</span>
                </a>
              </li>
            </ul>
          </nav>
        </b-col>
        <div class="w-100" v-if="$device.isDesktopOrTablet"></div>
      </b-row>
      <small class="footer-text text-gray-650 text-base mt-2_5 mb-2_5 footer-copyright" v-if="$device.isMobile">
        © 2019 Index. Все права защищены.
      </small>
    </b-container>
  </footer>
</template>

<script>
  import IndexUpLogo from './index-up-logo';
  import AndroidButton from './android-button';
  import IOSButton from './ios-button';
  import '@/components/shared/social-icons';
  import '@/components/icons/lock';

  export default {
    data() {
      return {
        help: [
          { text: "Депозиты", url: "#" },
          { text: "Выплаты", url: "#" },
          { text: "FAQ", url: "#" },
          { text: "Служба поддержки", url: "#" },
        ],
        service: [
          { text: "Ставки LIVE", url: "#" },
          { text: "Товарный знак", url: "#" },
          { text: "Бонусы и акции", url: "#" },
        ],
        index: [
          { text: "О компании", url: "#" },
          { text: "Правила и Условия", url: "#" },
          { text: "Партнерская программа", url: "#" },
          { text: "Политика конфиденциальности", url: "#" },
        ],
        cabinet: [
          { text: "Вход", url: "#" },
          { text: "Регистрация", url: "#" },
          { text: "Смена пароля", url: "#" },
        ],
        social: [
          { key: "twitter", text: "Твиттер", url: "#" },
          { key: "instagram", text: "Инстаграм", url: "#" },
          { key: "facebook", text: "Фейсбук", url: "#" },
          { key: "vkontakte", text: "Вконтакте", url: "#" },
        ],
      }
    },
    components: {
      IndexUpLogo,
      AndroidButton,
      IOSButton,
    }
  }
</script>

<style>
  .footer-title,
  .footer-list,
  .footer-text {
    line-height: 1.5rem;
  }
</style>

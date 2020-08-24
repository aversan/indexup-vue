<template>
  <b-row class="my-2 my-xl-4_75" no-gutters>
    <b-col cols="12" xl="6" class="mx-auto">
      <b-alert
        :class="{
      'main-main-alert text-center p-0 bg-transparent text-gray mb-0': true,
      'alert-mobile': $device.isMobile,
    }"
        show
      >
        {{ text }}
      </b-alert>
    </b-col>
  </b-row>
</template>

<script>
  export default {
    data() {
      return {
        text: "Мы за доли секунд находим самые высокие коэффициенты и агрегируем их в одном удобном интерфейсе просто фиктивный текст в полиграфии и вёрстке. Лорем Ипсум был стандартным манекенщиком в отрасли",
      }
    },
  }
</script>

<style lang="scss">
  .main-main-alert {
  }
</style>

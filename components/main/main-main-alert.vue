<template>
  <b-alert :show="$device.isDesktopOrTablet" variant="dark" class="main-main-alert text-center py-2_5 text-gray">
    {{ text }}
  </b-alert>
</template>

<script>
  export default {
    data() {
      return {
        text: "Мы нашли самые высокие коэффициенты на ближайщие ТОП-матчи!",
      }
    }
  }
</script>

<style lang="scss">
  .main-main-alert {
  }
</style>

<template>
  <nav v-if="$device.isDesktopOrTablet">
    <b-breadcrumb class="main-breadcrumb font-weight-semibold mb-0" :items="items"></b-breadcrumb>
  </nav>
</template>

<script>
  export default {
    data() {
      return {
        items: [
          {
            text: 'Главная',
            href: '#'
          },
          {
            text: 'Футбол',
            href: '#'
          },
          {
            text: 'Анлгия',
            href: '#'
          },
          {
            text: 'Премьер-лига',
            href: '#'
          },
          {
            text: 'Манчестер Юнайтед - Челси',
            active: true
          }
        ]
      }
    }
  }
</script>

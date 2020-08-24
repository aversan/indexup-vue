<template>
  <picture class="d-block text-center side-banner-container my-2">
    <source :srcset="image" type="image/jpg">
    <a class="side-banner-link" :href="url">
      <img class="side-banner rounded-xl img-fluid" :src="image" loading="lazy" :alt="alt" />
    </a>
  </picture>
</template>

<script>
  export default {
    props: ['image', 'url', 'alt'],
  }
</script>

<style lang="scss">
  .side-banner {}
</style>

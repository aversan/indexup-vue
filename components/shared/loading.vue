<template>
  <div
    :class="{
      'loading-page w-100 vh-100 position-fixed bg-dark justify-content-center align-items-center cover-background': true,
      'show': loading,
    }"
  >
    <IndexUpLogo />
  </div>
</template>

<script>
  import IndexUpLogo from '@/components/shared/index-up-logo';

  export default {
    head() {
      return {
        bodyAttrs: {
          class: this.loading ? 'is-loading-page overflow-hidden' : '',
        },
      }
    },
    data: () => ({
      loading: true,
    }),
    methods: {
      start () {
        this.loading = true;
      },
      finish () {
        this.loading = false;
      },
    },
    components: {
      IndexUpLogo,
    }
  }
</script>

<style lang="scss">
  .loading-page {
    top: 0;
    left: 0;
    z-index: 1100;
    overflow: hidden;
    transition: visibility 0s .333s, opacity .333s linear;
    opacity: 0;
    visibility: hidden;
    display: flex;
    pointer-events: none;
    cursor: default;

    .is-loading-page & {
      visibility: visible;
      opacity: 1;
      transition: opacity 1s linear;
    }
  }
</style>

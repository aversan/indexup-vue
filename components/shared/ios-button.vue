<template>
  <b-button class="h-6 w-6 d-inline-flex align-items-center justify-content-center text-white" variant="dark" pill href="#" target="_blank">
    <svgicon
      :class="{
        'h-2_5 w-2_5': $device.isMobile,
      }"
      name="apple"
    />
  </b-button>
</template>

<script>
  import '@/components/icons/apple';

  export default {
    components: {
    }
  }
</script>

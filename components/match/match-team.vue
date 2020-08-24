   <template>
     <div
       :class="{
          'd-flex flex-nowrap align-items-center match-team': true,
          'match-team-1': !second,
          'match-team-2 flex-row-reverse': second,
          'match-team-large': size == 'large',
          'match-team-medium': size == 'medium',
          'match-team-small': size == 'small',
        }"
     >
       <div class="flex-grow-1">
         <div
           :class="{
              'match-team-name': true,
              'text-right': !second,
              'text-left': second,
              'text-2xl font-weight-bold': size == 'large' && $device.isDesktopOrTablet,
              'text-xl font-weight-bold': size == 'large' && $device.isMobile,
              'text-sm-2 font-weight-semibold': size == 'medium' && $device.isDesktopOrTablet,
              'text-xl font-weight-semibold': size == 'medium' && $device.isMobile,
              'text-sm-2 font-weight-semibold':  size == 'small' && $device.isDesktopOrTablet,
              'text-xl font-weight-semibold':  size == 'small' && $device.isMobile,
            }"
         >
           {{ namesMap[name] }}
         </div>
       </div>
       <img
         v-if="!text"
         :class="{
          'match-team-logo cover-object flex-shrink-0': true,
          'ml-2_5':  size == 'large' && !second,
          'mr-2_5':  size == 'large' && second,
          'ml-2_25':  size == 'medium' && !second,
          'mr-2_25':  size == 'medium' && second,
          'ml-2':  size == 'small' && !second,
          'mr-2':  size == 'small' && second,
          'w-7_5 h-7_5':  size == 'large',
          'w-6 h-6':  size == 'medium',
          'w-3_75 h-3_75':  size == 'small',
        }"
        :src="logosMap[name]"
         alt=""
       >
     </div>
</template>

<script>
  export default {
    data() {
      return {
        logosMap: {
          'manchester-united': '/team-logos/manchester-united.svg',
          'chelsea': '/team-logos/chelsea.svg',
        },
        namesMap: {
          'manchester-united': 'Манчестер Юнайтед',
          'chelsea': 'Челси',
        },
      }
    },
    props: {
      name: {
        type: String,
        default: 'Нонейм',
      },
      logo: {
        type: String,
        default: 'http://placehold.it/60x60',
      },
      text: {
        type: Boolean,
        default: false,
      },
      second: {
        type: Boolean,
        default: false,
      },
      size: {
        type: String,
        default: 'large', // large medium small
      },
    },
    components: {
    },
  }
</script>

<style lang="scss">
.match-team {
  &-name {
    line-height: 1.2;
  }
}
</style>

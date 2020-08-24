<template>
  <article
    :class="{
      'match-info d-flex flex-nowrap align-items-center justify-content-center row no-gutters': true,
      'match-info-info': variant == 'info',
      'match-info-info-small': variant == 'info-small',
      'match-info-info-medium': variant == 'info-medium',
      'match-info-short': variant == 'short',
      'match-info-short-small': variant == 'short-small',
      'match-info-short-medium': variant == 'short-medium',
      'match-info-text': variant == 'text',
      'match-info-layout-center': layout == 'center',
      'match-info-layout-side': layout == 'side',
      'match-info-mobile': $device.isMobile,
    }"
  >
    <MatchTeam
      :class="{
        'col': layout == 'center',
        'col-auto': layout == 'side',
      }"
      name="manchester-united"
      :size="sizeTeamMap[variant]"
      :text="variant == 'text'"
    />
    <div class="match-info-sep text-center mx-1 col-auto" v-if="variant == 'text' && layout == 'side'">&ndash;</div>
    <div class="match-info-sep text-gray-525 w-5_5 mx-1 text-center col-auto" v-if="variant == 'short' || variant == 'short-small' || variant == 'short-medium'">vs</div>
    <MatchTeam
      :class="{
        'col': layout == 'center',
        'col-auto': layout == 'side',
      }"
      name="chelsea"
      :size="sizeTeamMap[variant]"
      :text="variant == 'text'"
      second
    />
    <div class="flex-grow-1" v-if="layout == 'side'"></div>
    <div
      :class="{
        'd-flex match-info-secondary order-2 col-auto': true,
        'flex-column text-center px-2_25': variant != 'text' && $device.isDesktopOrTablet,
        'flex-column text-center px-2': variant != 'text' && $device.isMobile,
        'flex-row align-items-center': variant == 'text' && $device.isDesktopOrTablet,
        'flex-row align-items-center': variant == 'text' && $device.isMobile,
      }"
      v-if="variant != 'short' && variant != 'short-small' && variant != 'short-medium'"
    >
      <strong
        :class="{
          'text-nowrap match-info-time': true,
        }"
      >
        19:30
      </strong>
      <small
        :class="{
          'text-nowrap text-gray-525 match-info-date': true,
        }"
      >
        15 января
      </small>
    </div>
  </article>
</template>

<script>
  import MatchTeam from '@/components/match/match-team';

  export default {
    data() {
      return {
        sizeTeamMap: {
          'info': 'large',
          'info-small': 'small',
          'info-medium': 'medium',
          'short': 'large',
          'short-small': 'small',
          'short-medium': 'medium',
          'text': 'small',
        },
      }
    },
    props: {
      variant: {
        type: String,
        default: 'info', // info info-medium info-small short short-medium short-small text
      },
      layout: {
        type: String,
        default: 'center', // center side
      },
    },
    components: {
      MatchTeam,
    },
  }
</script>

<style lang="scss">

  /*layout*/

  .match-info-layout-center {
    .match-team-1 {
      order: 1;
    }

    .match-team-2 {
      order: 3;
    }

    &.match-info-info .match-info-secondary,
    &.match-info-info-medium .match-info-secondary,
    &.match-info-info-small .match-info-secondary {
      order: 2;
    }

    &.match-info-short .match-info-sep,
    &.match-info-short-medium .match-info-sep,
    &.match-info-short-small .match-info-sep {
      order: 2;
    }
  }


  /*large*/

  .match-info-info .match-info-time,
  .match-info-short .match-info-time {
    font-size: var(--text-3xl);
  }

  .match-info-info.match-info-mobile .match-info-time,
  .match-info-short.match-info-mobile .match-info-time {
    font-size: var(--text-4xl);
  }

  .match-info-info .match-info-date,
  .match-info-short .match-info-date {
    font-size: var(--text-lg);
  }

  .match-info-info.match-info-mobile .match-info-date,
  .match-info-short.match-info-mobile .match-info-date {
    font-size: var(--text-xl);
  }

  .match-info-text.match-info-mobile .match-info-time {
    font-size: var(--text-2xl);
  }

  .match-info-text.match-info-mobile .match-info-date {
    font-size: var(--text-base);
  }


  /*medium*/

  .match-info-info-medium .match-info-time,
  .match-info-short-medium .match-info-time {
    font-size: var(--text-xl);
  }

  .match-info-info-medium .match-info-date,
  .match-info-short-medium .match-info-date {
    font-size: var(--text-sm);
  }
</style>

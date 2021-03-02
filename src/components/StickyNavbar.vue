
<template>
  <section>
    <header class="header">
      <div class="navbar">
        <twitch-icon></twitch-icon>
        <div class="navbar__text-box">
          <!-- <p class="navbar__text">Following</p> -->
          <p class="navbar__text">Browse</p>
        </div>
        <horizontal-dots></horizontal-dots>
        <div class="navbar__search">
          here the search bar
        </div>

      </div>
    </header>
  </section>
</template>

<script>
// import {ref} from 'vue';
import TwitchIcon from "./TwitchIcon";
import HorizontalDots from "./HorizontalDots";

export default {
  setup() {
    return {
      TwitchIcon,
      HorizontalDots,
    };
  },
};
</script>

<style lang="scss">
.header {
}
.navbar {
  display: flex;

  align-items: center;
  overflow: hidden;

  &__icon {
    width: 2rem;
    height: 2rem;
    // for testing
    border: solid 1px #9147ff;

    &--logo {
      fill: #9147ff;
    }
  }
  &__text-box {
    display: flex;
  }
  &__text {
  }
  &__hdots {
    position: relative;
    color: purple;
  }
}
</style>
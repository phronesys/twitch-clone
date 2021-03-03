
<template>
  <section>
    <div class="navbar">
      <twitch-icon></twitch-icon>
      <div class="navbar__left">
        <p v-if="isLogged">Following</p>
        <p>Browse</p>
      </div>
      <horizontal-dots></horizontal-dots>
      <form class="search">
        <input type="text" placeholder="Search" class="search__input" />
        <button class="search__button">
          <search-icon></search-icon>
        </button>
      </form>
      <div class="navbar__right">
        <prime-icon></prime-icon>
        <!-- not logged -->
        <button v-if="!isLogged" @click="logIn">Log In</button>
        <button v-if="!isLogged">Sign Up</button>
        <user-icon v-if="!isLogged"></user-icon>
        <!-- logged -->
        <notification-icon v-if="isLogged"></notification-icon>
        <whisper-icon v-if="isLogged"></whisper-icon>
        <base-button v-if="isLogged">
          Get Bits
          <bits-icon></bits-icon>
        </base-button>
        <div class="navbar__picture">
          <!-- <img src="../../public/img/runescape.png" alt="default user" /> -->
        </div>
      </div>
    </div>
  </section>
</template>

<script>
import { ref } from "vue";
// icons
import TwitchIcon from "./icons/TwitchIcon";
import HorizontalDots from "./icons/HorizontalDots";
import PrimeIcon from "./icons/PrimeIcon";
import SearchIcon from "./icons/SearchIcon";
import UserIcon from "./icons/UserIcon";
import NotificationIcon from "./icons/NotificationIcon";
import WhisperIcon from "./icons/WhisperIcon";
import BitsIcon from "./icons/BitsIcon";

import BaseButton from "./BaseButton";

export default {
  setup() {
    const isLogged = ref(false);

    function logIn() {
      isLogged.value = true;
    }

    return {
      TwitchIcon,
      HorizontalDots,
      PrimeIcon,
      SearchIcon,
      UserIcon,
      NotificationIcon,
      WhisperIcon,
      BitsIcon,
      BaseButton,
      isLogged,
      logIn,
    };
  },
};
</script>

<style lang="scss">
.navbar {
  margin: -8px -6px;
  display: flex;

  align-items: center;
  overflow: hidden;
  background-color: var(--color-navbar);
  &__left {
    display: flex;
    align-items: center;
  }
  &__right {
    display: flex;
    align-items: center;
  }

  &__icon {
    width: 2rem;
    height: 2rem;
    cursor: pointer;
    // for testing
    // border: solid 1px #9147ff;
    margin: 0 1rem;

    &--logo {
      fill: var(--color-primary);
    }
    &--light {
      fill: var(--color-grey-light);
    }
  }
  &__picture {
    width: 2.5rem;
    height: 2.5rem;
    background-color: var(--color-grey-dark);
    border-radius: 50%;
    background-image: url("../../public/img/runescape.png");
    background-size: cover;

  }

}
.search {
  margin: 0 auto;
  display: flex;
  align-items: stretch;
}
</style>
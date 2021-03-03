
<template>
  <section>
    <div class="navbar">
      <twitch-icon class="navbar__icon navbar__icon--logo"></twitch-icon>
      <div class="navbar__left">
        <h3 v-if="isLogged" class="navbar__left--text">Following</h3>
        <h3 class="navbar__left--text">Browse</h3>
      </div>
      <horizontal-dots class="navbar__icon navbar__icon--light"></horizontal-dots>
      <form class="search">
        <input type="text" placeholder="Search" class="search__input" />
        <button class="search__button">
          <search-icon class="navbar__icon navbar__icon--light"></search-icon>
        </button>
      </form>
      <div class="navbar__right">
        <prime-icon class="navbar__icon navbar__icon--light"></prime-icon>
        <!-- not logged -->
        <div v-if="!isLogged" class="navbar__right--logged-out">
          <button @click="logIn">Log In</button>
          <button>Sign Up</button>
          <user-icon class="navbar__icon navbar__icon--light"></user-icon>
        </div>
        <!-- logged -->
        <div v-else class="navbar__right--logged-in">
          <notification-icon class="navbar__icon navbar__icon--light"></notification-icon>
          <whisper-icon class="navbar__icon navbar__icon--light"></whisper-icon>
          <base-button class="navbar__icon--bits">
            <bits-icon class="navbar__icon navbar__icon--light"></bits-icon>
            Get Bits
          </base-button>
          <div class="navbar__picture">
            <!-- <img src="../../public/img/runescape.png" alt="default user" /> -->
          </div>
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
  height: 3rem;
  display: flex;

  align-items: center;
  overflow: hidden;
  background-color: var(--color-navbar);
  &__left {
    display: flex;
    align-items: center;
    &--text {
      margin-right: 1rem;
      margin-left: 1.5rem;
    }
  }
  &__right {
    display: flex;
    align-items: center;
    justify-content: center;
    &--logged-in {
      display: flex;
      align-items: center;
    }
  }

  &__icon {
    width: 1.2rem;
    height: 1.2rem;
    cursor: pointer;
    // for testing
    // border: solid 1px #9147ff;
    margin: 0 1rem;

    &--logo {
      width: 1.7rem;
      height: 1.7rem;
      fill: var(--color-primary);
    }
    &--bits {
      align-self: stretch;
    }
    &--light {
      fill: var(--color-grey-light);
    }
  }
  &__picture {
    width: 2.5rem;
    height: 2.5rem;
    margin: 0 0.7rem;
    background-color: var(--color-grey-dark-1);
    border-radius: 50%;
    background-image: url("../../public/img/runescape.png");
    background-size: cover;
  }
}
.search {
  margin: 7px auto;
  align-self: stretch;
  display: flex;
  align-items: stretch;
}
</style>
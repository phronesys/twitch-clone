
<template>
  <section>
    <div class="navbar">
      <twitch-icon class="navbar__icon navbar__icon--logo"></twitch-icon>
      <div class="navbar__left">
        <router-link to="/" v-if="isLogged" class="navbar__left--text"
          >Following</router-link
        >
        <router-link to="/about" class="navbar__left--text">Browse</router-link>
      </div>
      <horizontal-dots
        class="navbar__icon navbar__icon--light"
      ></horizontal-dots>
      <search-bar></search-bar>
      
      <div class="navbar__right">
        <prime-icon class="navbar__icon navbar__icon--light"></prime-icon>
        <span class="navbar__notification">7</span>
        <!-- not logged icons -->
        <div v-if="!isLogged" class="navbar__right--logged-out">
          <base-button @click="logIn">Log In</base-button>
          <base-button class="btn--primary">Sign Up</base-button>
        </div>
        <user-icon
          v-if="!isLogged"
          class="navbar__icon navbar__icon--light"
        ></user-icon>
        <!-- logged icons -->
        <div v-else class="navbar__right--logged-in">
          <notification-icon
            class="navbar__icon navbar__icon--light"
          ></notification-icon>
          <span class="navbar__notification">15</span>
          <whisper-icon class="navbar__icon navbar__icon--light"></whisper-icon>
          <base-button>
            <div class="navbar__button">
              <bits-icon></bits-icon>
              Get Bits
            </div>
          </base-button>
          <div class="navbar__picture"></div>
          <span class="navbar__picture--status">&bull;</span>
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
import UserIcon from "./icons/UserIcon";
import NotificationIcon from "./icons/NotificationIcon";
import WhisperIcon from "./icons/WhisperIcon";
import BitsIcon from "./icons/BitsIcon";

import BaseButton from "./BaseButton";
import SearchBar from "./SearchBar";

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
      UserIcon,
      NotificationIcon,
      WhisperIcon,
      BitsIcon,
      BaseButton,
      SearchBar,
      isLogged,
      logIn,
    };
  },
};
</script>

<style lang="scss">
.navbar {
  // margin: -8px -6px;
  height: 5rem;
  display: flex;

  align-items: center;
  // overflow: hidden;
  background-color: var(--color-navbar);
  // border-bottom: 2px solid black;
  box-shadow: var(--shadow-op);
  &__left {
    display: flex;
    align-items: center;
    &--text {
      text-decoration: none;
      // background-color: white;
      margin: 2rem;
      padding: 1rem 0;
      color: var(--color-grey-light);
      align-self: stretch;
      font-weight: 800;
      font-size: 1.8rem;
      // margin-right: 2rem;
      // margin-left: 2rem;
      &:hover {
        color: var(--color-primary);
      }
      // &:active {
      //   color: var(--color-primary);
      // }
      animation: all 1s;
      &.router-link-active {
        color: var(--color-primary-light);
        border-bottom: solid 2.5px var(--color-primary-light);
      }
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
    &--logged-out {
      display: flex;
      align-items: center;
      margin: -0.5rem 0.3rem;
    }
  }

  &__icon {
    width: 2.8rem;
    height: 2.8rem;
    cursor: pointer;
    // for testing
    // border: solid 1px #9147ff;
    border-radius: 5px;
    padding: 5px;
    margin: 0 0rem;
    align-self: center;

    &:hover {
      background-color: #464648;
    }

    &--logo {
      width: 3.7rem;
      height: 3.7rem;
      margin-left: .5rem;
      background-color: inherit;
      fill: var(--color-primary);
      &:hover {
        background-color: inherit;
      }
    }
    &--light {
      fill: var(--color-grey-light);
    }
    &--magnifying {
      fill: var(--color-magnifying);
      width: 2.5rem;
      height: 2.5rem;
    }
  }
  &__notification {
    background-color: var(--color-notification);
    color: var(--color-grey-light);
    font-weight: 700;
    font-size: 0.8rem;
    height: 1.5rem;
    width: 1.5rem;
    border-radius: 1000px;
    position: relative;
    top: -0.8rem;
    right: 1.3rem;
    display: flex;
    align-items: center;
    justify-content: center;
  }
  &__button {
    display: flex;
    align-items: center;
    margin: -0.2rem 0.3rem;
  }
  &__picture {
    width: 3rem;
    height: 3rem;
    margin: 0 0.7rem;
    background-color: var(--color-primary);
    border-radius: 50%;
    background-image: url("../../public/img/runescape.png");
    background-size: cover;
    &--status {
      position: relative;
      right: 1.8rem;
      top: 1rem;
      font-size: 2rem;
      color: var(--color-connected);
      z-index: 20;
      background-color: black;
      border-radius: 10000px;
      height: .9rem;
      width: .9rem;
      flex-direction: column;
      display: flex;
      justify-content: center;
      align-items: center;
    }
  }
}

</style>
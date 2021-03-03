
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
      <form class="search">
        <input type="text" placeholder="Search" class="search__input" />
        <button class="search__button">
          <search-icon class="navbar__icon--magnifying"></search-icon>
        </button>
      </form>
      <div class="navbar__right">
        <prime-icon class="navbar__icon navbar__icon--light"></prime-icon>
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
          <whisper-icon class="navbar__icon navbar__icon--light"></whisper-icon>
          <base-button>
            <div class="navbar__button">
              <bits-icon></bits-icon>
              Get Bits
            </div>
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
  // margin: -8px -6px;
  height: 5rem;
  display: flex;

  align-items: center;
  // overflow: hidden;
  background-color: var(--color-navbar);
  border-bottom: 2px solid black;
  &__left {
    display: flex;
    align-items: center;
    &--text {
      text-decoration: none;
      // background-color: white;
      margin: 2rem;
      padding:1rem 0;
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
    border-radius: 3px;
    padding: 5px;
    margin: 0 0.6rem;
    align-self: center;

    &:hover {
      background-color: #464648;
    }

    &--logo {
      width: 3.7rem;
      height: 3.7rem;
      background-color: white;
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
  }
}
.search {
  flex: 0 0 25%;
  margin: 7px auto;
  align-self: stretch;
  display: flex;

  &__input {
    font-family: inherit;
    border-radius: 6px 0 0 6px;
    min-width: 37rem;
    max-width: 37rem;
    border: none;
    padding-left: 1.5rem;
    margin-right: 0.1rem;

    // font-size: inherit;
    background-color: var(--color-grey-dark-4);

    &:focus {
      outline: none;
      border: 2px solid var(--color-primary);
      background-color: #000;
      outline-offset: 0;
    }
    &::-webkit-input-placeholder {
      font-weight: 500;
      color: var(--color-grey-light);
    }
  }
  // &__input:focus + &__button {
  //   background-color: #000;
  // }
  &__button {
    background-color: var(--color-grey-dark-2);
    border-radius: 0 6px 6px 0;
    padding: 0 0.5rem;
    border: none;
  }
}
</style>
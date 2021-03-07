<template>
  <section>
    <div class="sidebar__title-box">
      <div class="sidebar__title">Recommended Channels</div>
      <div class="sidebar__icon">icon</div>
    </div>
    <ul>
      <li v-for="channel in channels" :key="channel">
        <div class="channel">
          <img class="channel__picture" :src="channel.picture" alt="picture" />
          <div class="channel__details">
            <h3 class="channel__details--username">{{ channel.username }}</h3>
            <p class="channel__details--playing">{{ channel.playing }}</p>
          </div>
          <div class="channel__viewers">
            <span class="channel__viewers--dot">&bull;</span>
            <span class="channel__viewers--number">
              {{ channel.viewers }}
            </span>
          </div>
        </div>
      </li>
    </ul>
    <div class="community">
      <div class="community__text">
        <h2 class="community__header">
          Join the
          <span style="color: var(--color-primary-light)">Twitch</span>
          community!
        </h2>
        <p class="community__paragraph">
          Discover the best live streams anywhere.
        </p>
      </div>
      <base-button class="btn--primary community__button">Sign up</base-button>
    </div>
  </section>
</template>

<script>
import BaseButton from "./BaseButton";
export default {
  components: {
    BaseButton,
  },
  data() {
    return {
      channels: [
        {
          picture:
            "https://static-cdn.jtvnw.net/jtv_user_pictures/905af69a-4fd8-42c7-b842-bf4ee4d51b3b-profile_image-70x70.png",
          username: "Tubbo",
          playing: "Minecraft",
          viewers: "82.8K",
        },
        {
          picture:
            "https://static-cdn.jtvnw.net/jtv_user_pictures/a2592e98-5ba6-4c9a-9d9e-cf036d6f64c2-profile_image-70x70.jpg",
          username: "Rubius",
          playing: "Just Chatting",
          viewers: "58.9K",
        },
        {
          picture:
            "https://static-cdn.jtvnw.net/jtv_user_pictures/a2592e98-5ba6-4c9a-9d9e-cf036d6f64c2-profile_image-70x70.jpg",
          username: "Rubius",
          playing: "Just Chatting",
          viewers: "58.9K",
        },
        {
          picture:
            "https://static-cdn.jtvnw.net/jtv_user_pictures/a2592e98-5ba6-4c9a-9d9e-cf036d6f64c2-profile_image-70x70.jpg",
          username: "Rubius",
          playing: "Just Chatting",
          viewers: "58.9K",
        },
        {
          picture:
            "https://static-cdn.jtvnw.net/jtv_user_pictures/a2592e98-5ba6-4c9a-9d9e-cf036d6f64c2-profile_image-70x70.jpg",
          username: "Rubius",
          playing: "Just Chatting",
          viewers: "58.9K",
        },
        {
          picture:
            "https://static-cdn.jtvnw.net/jtv_user_pictures/a2592e98-5ba6-4c9a-9d9e-cf036d6f64c2-profile_image-70x70.jpg",
          username: "Rubius",
          playing: "Just Chatting",
          viewers: "58.9K",
        },
        {
          picture:
            "https://static-cdn.jtvnw.net/jtv_user_pictures/a2592e98-5ba6-4c9a-9d9e-cf036d6f64c2-profile_image-70x70.jpg",
          username: "Rubius",
          playing: "Just Chatting",
          viewers: "58.9K",
        },
        {
          picture:
            "https://static-cdn.jtvnw.net/jtv_user_pictures/a2592e98-5ba6-4c9a-9d9e-cf036d6f64c2-profile_image-70x70.jpg",
          username: "Rubius",
          playing: "Just Chatting",
          viewers: "58.9K",
        },
        {
          picture:
            "https://static-cdn.jtvnw.net/jtv_user_pictures/a2592e98-5ba6-4c9a-9d9e-cf036d6f64c2-profile_image-70x70.jpg",
          username: "Rubius",
          playing: "Just Chatting",
          viewers: "58.9K",
        },
        {
          picture:
            "https://static-cdn.jtvnw.net/jtv_user_pictures/a2592e98-5ba6-4c9a-9d9e-cf036d6f64c2-profile_image-70x70.jpg",
          username: "Rubius",
          playing: "Just Chatting",
          viewers: "58.9K",
        },

        // { picture: "", username: "", playing: "", viewers: "" },
      ],
    };
  },
};
</script>

<style lang="scss">
.sidebar {
  flex: 0 0 24rem;
  overflow-y: scroll;
  // width: 24rem;
  background-color: var(--color-sidebar);
  height: 95vh;

  top: 0;
  left: 0;
  margin: auto;
  &__title-box {
    display: flex;
    padding: 1.6rem 1rem;
    margin-bottom: -0.6rem;
    justify-content: space-between;
  }
  &__title {
    text-transform: uppercase;
    font-weight: bolder;
    font-size: 1.2rem;
    letter-spacing: 0.7px;
  }
  &__icon {
    margin-right: 0.95rem;
  }
}

.channel {
  padding: 0.5rem;
  width: 100%;
  display: flex;
  justify-content: space-between;
  align-items: center;
  &:hover {
    background-color: var(--color-sidebar-hover);
  }
  &__picture {
    border-radius: 50%;
    width: 3rem;
    margin-left: 0.4rem;
  }
  &__details {
    margin: 0;
    margin-left: 1rem;
    margin-right: auto;
    &--username {
      font-size: 1.4rem;
    }
    &--playing {
      font-size: 1.3rem;
      font-weight: lighter;
      color: var(--color-grey-light-2);
    }
  }
  &__viewers {
    font-size: 1.3rem;
    margin-right: 0.4rem;
    letter-spacing: 0.7px;
    display: flex;
    align-items: center;
    &--dot {
      color: red;
      font-size: 2.5rem;
      position: relative;
      top: -0.6rem;
    }
    &--number {
      position: relative;
      top: -0.5rem;
    }
  }
}
.community {
  margin: 1rem;
  padding: 2rem;
  border-radius: 8px;
  box-shadow: var(--shadow-op);
  background-color: var(--color-navbar);
  &__text {
    display: flex;
    flex-direction: column;
    margin-bottom: 1rem;
  }

  &__header {
    font-size: 2.45rem;
    margin: 1rem 0;
  }
  &__paragraph {
    font-size: 1.45rem;
  }
  &__button {
    margin: 0;
  }
  margin-bottom: 3rem;
}
</style>
<template>
  <section>
    <div class="sidebar__title-box">
      <div class="sidebar__title">Recommended Channels</div>
      <div class="sidebar__icon">icon</div>
    </div>
    <div class="channel">
      <ul>
        <li v-for="channel in channels" :key="channel">
          <img class="channel__picture" :src="channel.picture" alt="picture" />
          <h3 class="channel__username">{{ channel.username }}</h3>
          <p class="channel__playing">{{ channel.playing }}</p>
          <div class="channel__live">&bull;</div>
          <span class="channel__viewers">
            {{ channel.viewers }}
          </span>
        </li>
      </ul>
    </div>
  </section>
</template>

<script>
export default {
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
        // { picture: "", username: "", playing: "", viewers: "" },
      ],
    };
  },
};
</script>

<style lang="scss">
.sidebar {
  // config on home
  &__title-box {
    display: flex;
    padding: 1.8rem 1rem;
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
  &__picture {
    border-radius: 50%;
    width: 3rem;
  }
  &__username {
    
  }
  &__live {
    color: red;
    font-size: 2.5rem;
  }
}
</style>
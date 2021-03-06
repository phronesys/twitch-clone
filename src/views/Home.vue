<template>
  <div class="home">
    <video-content class="content"></video-content>
    <div class="bar__scroll"></div>
  </div>
</template>

<script>
// @ is an alias to /src
import VideoContent from "../components/VideoContent";

export default {
  name: "Home",
  components: {
    VideoContent,
  },
  setup() {},
};
</script>

<style lang="scss">
.home {
  margin-top: 5rem;
  display: flex;
  // overflow-y: scroll;
  overflow: auto;
}
.content {
  margin-left: 24rem;
  flex: 1;
  //testing
  height: 120vh;
}
.bar {
  &__scroll {
    width: 1rem;
    overflow: auto;
    // background-color: white;
    min-height: 10px;
    box-shadow: 0 0 1px 1px hsl(0deg 0% 100% / 25%);
    background-color: var(--color-grey-dark-1);
  }

  &__scroll::-webkit-scrollbar-track {
    background-color: red;
  }

  &__scroll::-webkit-scrollbar {
    width: 12px;
    background-color: #f5f5f5;
  }

  &__scroll::-webkit-scrollbar-thumb {
    border-radius: 10px;
    -webkit-box-shadow: inset 0 0 6px rgba(0, 0, 0, 0.3);
    background-color: #555;
  }
}
</style>

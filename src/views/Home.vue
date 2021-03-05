<template>
  <div class="home">
    <video-content class="content"></video-content>
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
}
.sidebar {
  position: fixed;
  width: 24rem;
  background-color: var(--color-sidebar);
  height: 95vh;

  top: 0;
  left: 0;
  margin: auto;
  margin-top: 5rem;
}
.content {
  margin-left: 24rem;
  flex: 1;
  //testing
  height: 120vh;
}
</style>

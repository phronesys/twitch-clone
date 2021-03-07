<template>
  <div class="video">
    <vueper-slides bullets-outside :dragging-distance="50">
      <vueper-slide
        v-for="(slide, i) in slides"
        :key="i"
        :video="slide.video"
      />
    </vueper-slides>
  </div>
</template>

<script>
import { VueperSlides, VueperSlide } from "vueperslides";
import "vueperslides/dist/vueperslides.css";
export default {
  data: () => ({
    slides: [
      {video: "https://youtube.com/embed/8TCxE0bWQeQ?controls=0&fs=0&modestbranding=1&color=white&iv_load_policy=3&autohide=1&enablejsapi=1"},
      {
        video:
          "https://youtube.com/embed/Z_DWo_HqXws?controls=0&fs=0&modestbranding=1&color=white&iv_load_policy=3&autohide=1&enablejsapi=1",
      },
      {video:"https://youtube.com/embed/c7BVtGnlxT8?controls=0&fs=0&modestbranding=1&color=white&iv_load_policy=3&autohide=1&enablejsapi=1"},
      {
        video:
          "https://www.youtube.com/embed/2Jk26leBaEc?controls=0&fs=0&modestbranding=1&color=white&iv_load_policy=3&autohide=1&enablejsapi=1",
      },
      {
        video: "https://youtube.com/embed/dddR4ZpTDC0?controls=0&fs=0&modestbranding=1&color=white&iv_load_policy=3&autohide=1&enablejsapi=1"
      }
    ],
  }),
  components: {
    VueperSlides,
    VueperSlide,
  },
};
</script>

<style lang="scss">
.video {
  margin: 0 auto;
  width: 30rem;
  height: 20rem;
  // background-color: var(--color-grey-light);

  &__slides {
    color: var(--color-grey-light);
  }
  &__slide {
    color: var(--color-grey-light);
  }
}
</style>
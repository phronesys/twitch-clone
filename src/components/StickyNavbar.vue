<template>
  <section>
    <header class="header">
      <div class="navbar">
        <svg class="navbar__logo">
          <use xlink:href="../assets/sprites.svg#icon-twitch"></use>
        </svg>
        <div class="navbar__text-box">
          <p class="navbar__text">Following</p>
          <p class="navbar__text">Browse</p>
        </div>
        <svg class="navbar__hdots">
          <use xlink:href="@/assets/SVG/bubbles3.svg"></use>
        </svg>
      </div>
    </header>
  </section>
</template>

<script>
export default {};
</script>

<style lang="scss">
.header {
}
.navbar {
  display: flex;

  align-items: center;

  &__logo {
    width: 2rem;
    fill: #9147ff;
  }
  &__text-box {
    display: flex;
    margin-left: auto;
  }
  &__text {
  }
  &__hdots {
    position: relative;
    color: purple;
  }
}
</style>
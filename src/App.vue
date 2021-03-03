<template>
  <!-- <div id="nav">
    <router-link to="/">Home</router-link> |
    <router-link to="/about">About</router-link>
  </div> -->
  <sticky-navbar></sticky-navbar>
  <router-view />
</template>

<script>
import StickyNavbar from './components/StickyNavbar';
export default {
  setup() {
    return{
      StickyNavbar
    }
  },
};
</script>
<style lang="scss">
@import url('https://fonts.googleapis.com/css2?family=Inter&display=swap');
#app {
  // font-family: Avenir, Helvetica, Arial, sans-serif;
  font-family: var(--font);
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  // text-align: center;
  color: var(--color-grey-light);
  // background-color: black;
}
html {
  background-color: var(--color-bg);
}

:root {
  --font: Inter, "Helvetica Neue", Helvetica, Arial, sans-serif;


  //colors
  --color-bg:#0e0e10;
  --color-navbar: #18181b;

  --color-primary: #9147ff;

  --color-grey-light:#efeff1;
  --color-grey-dark-1: #1f1f23;
  --color-grey-dark-2: #3a3a3d; 
  --color-grey-dark-3: #464648;

}
</style>

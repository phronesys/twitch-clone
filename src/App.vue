<template>
  <!-- <div id="nav">
    
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
body {
  // font-family: Avenir, Helvetica, Arial, sans-serif;
  font-family: var(--font);
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  // text-align: center;
  color: var(--color-grey-light);
  // background-color: black;
  min-height: 100vh;
}
* {
  padding: 0;
  margin: 0;
}
html {
  background-color: var(--color-bg);
  box-sizing: border-box;
  font-size: 62.5%;
}
*,
*::before,
*::after {
  box-sizing: inherit;
}

:root {
  --font: Inter, "Helvetica Neue", Helvetica, Arial, sans-serif;


  //colors
  --color-bg:#0e0e10;
  --color-navbar: #18181b;
  --color-sidebar: var(--color-grey-dark-1);
  --color-magnifying: #5a5a5c;
  --color-notification: #e91916;
  --color-connected: #00f593;

  --color-primary: #9147ff;
  --color-primary-light: #a970ff;
  --color-primary-dark: #7f2aff;

  --color-grey-light:#efeff1;
  --color-grey-dark-1: #1f1f23;
  --color-grey-dark-2: #29292b;
  --color-grey-dark-3: #3a3a3d; 
  --color-grey-dark-4: #464648;


}
</style>

<template>
  <!-- <div id="nav">
    
  </div> -->
  <sticky-navbar class="header"> </sticky-navbar>
  <div class="content">
    <side-bar class="sidebar"></side-bar>
    <router-view class="router"/>
  </div>
</template>

<script>
import StickyNavbar from "./components/StickyNavbar";
import SideBar from "./components/SideBar";
export default {
  setup() {
    return {
      StickyNavbar,
      SideBar,
    };
  },
};
</script>
<style lang="scss">
@import url("https://fonts.googleapis.com/css2?family=Inter&display=swap");
.content {
  display: flex;
}
.router {
  flex: 1;
}
body {
  // font-family: Avenir, Helvetica, Arial, sans-serif;
  font-family: var(--font);
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  // text-align: center;
  color: var(--color-grey-light);
  // background-color: black;
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
*::-webkit-scrollbar {
  display: none;
}
*,
*::before,
*::after {
  box-sizing: inherit;
}
// .header {
//   position: fixed;
//   top: 0;
//   left: 0;
//   width: 100%;
// }

:root {
  --font: Inter, "Helvetica Neue", Helvetica, Arial, sans-serif;

  --shadow: 0 2px 4px rgba(0, 0, 0, 0.9);
  --shadow-op: 0 1px 2px rgba(0, 0, 0, 0.9), 0 0 2px rgba(0, 0, 0, 0.9);
  //colors
  --color-bg: #0e0e10;
  --color-navbar: #18181b;
  --color-sidebar: var(--color-grey-dark-1);
  --color-sidebar-hover: #2a282eb0;
  --color-magnifying: var(--color-grey-light-3);
  --color-notification: #e91916;
  --color-connected: #00f593;

  --color-primary: #9147ff;
  --color-primary-light: #a970ff;
  --color-primary-dark: #7f2aff;

  --color-grey-light: #efeff1;
  --color-grey-light-2: #c0c0c0;
  --color-grey-light-3: #5a5a5c;

  --color-grey-dark-1: #1f1f23;
  --color-grey-dark-2: #29292b;
  --color-grey-dark-3: #3a3a3d;
  --color-grey-dark-4: #464648;
}
</style>

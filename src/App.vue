<template>
  <div id="app">
    <router-view />
    <button class="scroll-button" v-if="scrolled" @click="scrollToTop">
      ^
    </button>
  </div>
</template>

<script lang="ts">
import { Component, Vue } from "vue-property-decorator";

@Component({})
export default class App extends Vue {
  private scrolled = false;

  mounted() {
    document.addEventListener("scroll", this.showScrollToTopButton);
  }

  public scrollToTop() {
    window.scrollTo({
      top: 0,
      left: 0,
      behavior: "smooth",
    });
  }

  public showScrollToTopButton() {
    document.body.scrollTop > 250 || document.documentElement.scrollTop > 250
      ? (this.scrolled = true)
      : (this.scrolled = false);
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
.scroll-button {
  position: fixed;
  bottom: 1rem;
  right: 1rem;
  height: 4rem;
  width: 4rem;
  border: 1px solid white;
  border-radius: 2rem;
  background-color: royalblue;
  color: white;
}
</style>

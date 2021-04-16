<template>
  <div class="home-view">
    <div class="title">The Recipeh Project</div>
    <div class="recipe-list">
      <router-link
        class="recipe-items"
        v-for="(v, i) in recipes"
        :key="i"
        :to="{ name: 'recipe', params: { recipe: v } }"
      >
        {{ v }}
      </router-link>
    </div>
  </div>
</template>

<script lang="ts">
import { Component, Vue } from "vue-property-decorator";

@Component({})
export default class HomeView extends Vue {
  private recipes: string[] = [
    "Omurice",
    "Onigiri",
    "Cup_Ramen",
    "Steak",
    "Cake",
    "Pie",
  ];
}
</script>

<style lang="scss">
@media screen and (min-width: 1024px) {
}
@media screen and (min-width: 768px) and (max-width: 1023px) {
}
@media screen and (max-width: 767px) {
  .title {
    font-size: 2rem;
  }
  .recipe-list {
    margin: 0.5rem 0;
    .recipe-items {
      display: block;
      font-size: 1.5rem;
      color: black;
      text-decoration: none;

      &:hover {
        background-color: silver;
      }

      &:active {
        color: white;
        background-color: royalblue;
        text-decoration: underline;
      }
    }
  }
}
</style>

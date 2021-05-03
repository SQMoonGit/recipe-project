<template>
  <div class="home-view">
    <div class="title">
      <button class="add-button">Remove Recipe</button>
      <span>The Recipeh Project</span>
      <button class="add-button">Add Recipe</button>
    </div>
    <div class="recipe-list">
      <img class="recipe-pic" />
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
.title {
  display: flex;
  justify-content: space-evenly;
}

.recipe-list {
  display: flex;
  flex-flow: column wrap;

  .recipe-items {
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
.add-button {
  cursor: pointer;
  font-size: 18px;
  border-radius: 4rem;
  border: 1px solid white;
  background-color: royalblue;
  color: white;

  &:hover {
    background-color: #91a8ee;
  }
}

@media screen and (min-width: 1024px) {
  .title {
    font-size: 3rem;
  }

  .recipe-list .recipe-items {
    font-size: 2.5rem;
  }
}
@media screen and (min-width: 768px) and (max-width: 1023px) {
  .title {
    font-size: 2.5rem;
  }

  .recipe-list .recipe-items {
    font-size: 2rem;
  }
}
@media screen and (max-width: 767px) {
  .title {
    font-size: 2rem;
  }

  .recipe-list .recipe-items {
    font-size: 1.5rem;

    .recipe-pic {
      display: none;
    }
  }
}
</style>

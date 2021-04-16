<template>
  <div>
    <div class="title">The Recipeh Project</div>
    <div>
      <span class="recipe-items" v-for="(v, i) in recipes" :key="i">
        {{ v }}
      </span>
    </div>
  </div>
</template>

<script lang="ts">
import { Component, Vue } from "vue-property-decorator";

@Component({})
export default class RecipeView extends Vue {
  private recipes: string[] = ["Omurice", "Onigiri", "Cup Ramen"];
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
  .recipe-items {
    display: block;
  }
}
</style>

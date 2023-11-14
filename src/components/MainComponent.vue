<template>
  <div class="row g-3 py-3">
    <CardComponent v-for="(el, index) in store.cardList" :key="index"
      :image="el.card_images[0].image_url"
      :name="el.name"
      :archetype="el.archetype" />
  </div>
</template>

<script>
import CardComponent from "./CardComponent.vue";
import { store } from "../data/store";
export default {
  name: "MainComponent",
  components: {
    CardComponent,
  },
  data() {
    return {
      store,
    };
  },
  methods: {},
};
</script>

<style lang="scss" scoped>


</style>

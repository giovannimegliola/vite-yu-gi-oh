<template>
  <header>
    <HeaderComponent class="text-center" title="Yu-Gi-Oh Api" />
  </header>
  <main class="container">
    <MainComponent />
  </main>
</template>

<script>
import {store} from "./data/store.js";
import axios from "axios";
import HeaderComponent from "./components/HeaderComponent.vue";
import MainComponent from "./components/MainComponent.vue";
  export default {
    name: "App",
    components: ( HeaderComponent, MainComponent),
    data (){
      return{
        store
      };
    },
    methods: {
      getCards(){
        const url = this.store.apiUrl + store.endPoint.name;
        axios.get(url).then((response) => {
          store.cardList = response.data.results;
        });
      },
    },
    created() {
      this.getCards();
    },
    
  };
</script>

<style lang="scss" scoped>

</style>
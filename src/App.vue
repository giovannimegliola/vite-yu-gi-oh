<template>
  <header>
    <HeaderComponent class="text-center" />
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
    components: {HeaderComponent, MainComponent},
    data (){
      return{
        store
      };
    },
    methods: {
      getCards(){
        const url = this.store.apiUrl + store.endPoint;
        axios.get(url).then((response) => {
          store.cardList = response.data.data;
          console.log(response.data.data);
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
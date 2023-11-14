<template>
  <header>
    <HeaderComponent class="text-center" />
  </header>
  <main class="container">
    <SearchBar @filterChange="filteredList" />
    <MainComponent />
  </main>
</template>

<script>
import {store} from "./data/store.js";
import axios from "axios";
import HeaderComponent from "./components/HeaderComponent.vue";
import MainComponent from "./components/MainComponent.vue";
import SearchBar from "./components/SearchBar.vue";
  export default {
    name: "App",
    components: {HeaderComponent, MainComponent, SearchBar},
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
      filteredList(selectedValue){
        const apiUrl = `https://db.ygoprodeck.com/api/v7/cardinfo.php?archetype=${selectedValue}`;
        axios.get(apiUrl).then((response) => {    
        store.filteredCardList = response.data.data;
        console.log(response.data.data);
      });  
    }
  },
    created() {
      this.getCards();
    },
    
  };
</script>

<style lang="scss" scoped>


</style>
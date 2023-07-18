<script>
  import HeaderComponent from './components/HeaderComponent.vue';
  import MainComponent from './components/MainComponent.vue';
  import FooterComponent from './components/FooterComponent.vue';
  import axios from "axios";
  import {store} from "./store.js"
  export default {
  data() {
    return {
      store,
    }
  },
  methods: {
    // getArchetype(){
    //   axios
    //         .get("https://db.ygoprodeck.com/api/v7/archetypes.php", {
    //           params: {
    //             archetype: this.store.searchArchetype
    //           }
    //         })
    //         .then(response =>{
    //           console.log(response.data)
    //           this.store.archetypes = response.data
    //         })
            
    // }
  },
  created() {
    axios
        .get("https://db.ygoprodeck.com/api/v7/cardinfo.php?num=20&offset=0")
        .then(response => {
          console.log(response.data);
          this.store.cards = response.data
        });

        this.getArchetype()
  },
  components: {
    HeaderComponent,
    MainComponent,
    FooterComponent,
  }
}

</script>

<template>
    <HeaderComponent/>
    <MainComponent/>
    <FooterComponent/>
    
</template>

<style lang="scss">
@use "assets/scss/style.scss"
</style>

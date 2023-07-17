<script>
  import HeaderComponent from './components/HeaderComponent.vue';
  import MainComponent from './components/MainComponent.vue';
  import FooterComponent from './components/FooterComponent.vue';
  import axios from "axios";
  export default {
  data() {
    return {
      
    }
  },
  methods: {},
  created() {
    axios
        .get("https://db.ygoprodeck.com/api/v7/cardinfo.php?num=20&offset=0")
        .then(response => {
          console.log(response.data);
        });
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

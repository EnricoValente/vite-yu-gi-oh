<script>
  import {store} from "../store.js"
  export default {
  data() {
    return {
      store,
    //   currentImage:0
    }
  }
}

</script>

<template>
    <main>
        
        <div class="row">
            <div class="col-2 p-3">
                <select class="form-select" aria-label="Default select example">
                    <option selected>Alien</option>
                    <option value="1">One</option>
                    <option value="2">Two</option>
                    <option value="3">Three</option>
                </select>
            </div>
        </div>

        

        <div class="container bg-white">
            <div class="row">
                <div class="col-12 col-sm-6 col-md-4 col-lg-3 text-center single-card mt-3" v-for="(card, index) in store.cards.data" :key="index">
                    <div class="img-box" v-for="(cardImage, i) in card.card_images" :key="i">
                        
                        <img :src="cardImage.image_url_small" alt="">
                    </div>
                    
                    <div class="card-description">
                        
                        <div class="text-white card-name">
                            
                            {{ card.name }}
                            
                        </div>
    
                        <div>
                            {{ card.archetype }}
                        </div>
                    </div>
                   
                        
                </div>
            </div>
        </div>

    </main>
</template>

<style scoped lang="scss">
  main {
    background-color: #D48F38;

   

    img {
        max-width: 168px;
    }

    .card-description {
        background-color: #D48F38;
        max-width: 168px;
        margin: auto;
        
    }
  

  }
</style>
<script>
  import {store} from "../store.js"
  export default {
  data() {
    return {
      store,
    
    }
  }
}

</script>

<template>
    <main>
        
        <div class="row align-items-center">
            <div class="col-2 p-3">
                <select v-model="store.searchArchetype" class="form-select" aria-label="Default select example">
                    
                    <option v-for="(archetype, i) in store.archetypes" :key="i" :value="archetype.archetype_name">{{ archetype.archetype_name }}</option>
                </select>
            </div>

            <div class="col-2">
                
                <button class="btn btn-primary" @click="$emit('search')">
                    Search
                </button>
            </div>

                   
                    
        </div>

        

        <div class="container bg-white">
           <div class="box pt-5">
               <div class="row">
                   
                   <div class="col-12 col-sm-6 col-md-4 col-lg-3 text-center single-card pt-3" v-for="(card, index) in store.cards" :key="index">
   
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

        </div>

    </main>
</template>

<style scoped lang="scss">
  main {
    background-color: #D48F38;

   .box {
    max-width: 800px;
    margin: auto;
   }

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
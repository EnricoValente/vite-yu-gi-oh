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

        

        <div class="container">
            <div class="row">
                <div class="col-12 col-sm-6 col-md-4 col-lg-3" v-for="(card, index) in store.cards" :key="index">
                    <div>
                        {{ card }}
                        <img src="" alt="">
                    </div>

                    <div>
                        <h2>
                            NOME
                        </h2>
                    </div>

                    <div>
                        TIPO
                    </div>
                </div>
            </div>
        </div>

    </main>
</template>

<style scoped lang="scss">
  main {
    background-color: #D48F38;
  }
</style>
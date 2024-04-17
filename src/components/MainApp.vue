<script>
import Card from "./Card.vue"
import { store } from "../store.js"

  export default {
    components:{
      Card,
        
    },
    data(){
        return{
          store
        }
    }
  }
</script>


<template>
  <main class="section py-5 px-4">
    <div class="container-fluid">
        <div class="row gy-5">
          <ul class="col-4 d-flex justify-content-center text-center"
          v-for="(movie, i) in store.movies" :key="movie.id" 
          v-if="store.movies.length !== 0"
          >
            <Card :item="movie" />
          </ul>
          <p v-else>Nessun film</p>
          <ul class="col-4 d-flex justify-content-center text-center" 
          v-for="(serie, i) in store.series" :key="serie.id" 
          v-if="store.series.length !== 0"
          >
            <Card :item="serie" />
          </ul>
          <p v-else>Nessuna serie</p>
        </div>
    </div>

  </main>
</template>


<style lang="scss" scoped>

</style>
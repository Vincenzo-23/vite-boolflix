<script>
import CardComponentMovie from "./CardComponentMovie.vue"
import CardComponentSerie from "./CardComponentSerie.vue"
import { store } from "../store.js"

  export default {
    components:{
        CardComponentMovie,
        CardComponentSerie,
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
            <div class="col-4 d-flex justify-content-center text-center" v-for="(movie, i) in store.movies" :key="movie.id" >
                <CardComponentMovie :movies="movie" />
            </div>
            <div class="col-4 d-flex justify-content-center text-center" v-for="(serie, i) in store.series" :key="serie.id" >
                <CardComponentSerie :series="serie" />
            </div>
        </div>
    </div>

  </main>
</template>


<style lang="scss" scoped>

</style>
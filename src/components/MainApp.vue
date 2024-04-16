<script>
import CardComponent from "./CardComponent.vue"
import { store } from "../store.js"

  export default {
    components:{
        CardComponent,
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
            <div class="col-4" v-for="(movie, i) in store.movies" :key="movie.id" >
                <CardComponent :card="movie"/>
            </div>
        </div>
    </div>

  </main>
</template>


<style lang="scss" scoped>

</style>
<script>
import { store } from "../store.js"
import axios from "axios"

  export default {
    data(){
        return{
            query: "",
            API_KEY: "361d6824b040c59dc3ba6d0a8e180efe"
        }
    },
    methods: {
        fetchItem(){
            axios.get(`https://api.themoviedb.org/3/search/movie`, {
                params: {
                    api_key: this.API_KEY,
                    query: this.query,
                }
            })
            .then((res) => {
                store.movies = res.data.results
                
            })
        }
    }
  }
</script>


<template>
  <header class="section p-4">
    <div class="container-fluid">
        <div class="row">
            <div class="logo col-auto me-auto">
                logo
            </div>
            <div class="col-auto">
                <input type="search" v-model="query">
            </div>
            <div class="col-auto">
                <button @click="fetchItem()">Search</button>
            </div>
        </div>
    </div>
  </header>
</template>


<style lang="scss" scoped>

</style>
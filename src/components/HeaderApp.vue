<script>
import { store } from "../store.js"
import axios from "axios"

  export default {
    data(){
        return{
            query: "",
            API_KEY: "e99307154c6dfb0b4750f6603256716d"
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
            
            axios.get(`https://api.themoviedb.org/3/search/tv`, {
                params: {
                    api_key: this.API_KEY,
                    query: this.query,
                }
            })
            .then((res) => {
                store.series = res.data.results
            })
        },
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
                <input type="search" v-model="query" @keyup.enter="fetchItem()" placeholder="Search...">
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
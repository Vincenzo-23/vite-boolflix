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
        <div class="row align-items-center">
            <div class="logo col-auto me-auto">BOOLFLIX</div>
            <input class="col-auto search_bar" type="search" v-model="query" @keyup.enter="fetchItem()" placeholder="Search...">
            <button class="col-auto search_btn" @click="fetchItem()">Search</button>
        </div>
    </div>
  </header>
</template>


<style lang="scss" scoped>
.section{
    background-color: black;
}
.logo{
    color: red;
    font-size: 36px;
}
.search_bar,
.search_btn{
    height: 30px;

}
.search_bar{
    margin-right: 20px;
    border: none;
    outline: none;
}


</style>
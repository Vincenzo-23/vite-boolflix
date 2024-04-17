<script>
  export default {
    props: {
      item: {
        type: Object,
        required: true
      }
    },
    data(){
      return{
        rating: Math.ceil(this.item.vote_average/2),
        imagePath: "https://image.tmdb.org/t/p/",
        poster_sizes: [
          "w92",
          "w154",
          "w185",
          "w342",
          "w500",
          "w780",
          "original"
        ],
        
      }
    }
  }
</script>


<template>
  <li class="card card_size movies">
    <div class="poster">
      <img v-if="item.poster_path !== null" :src="`${this.imagePath}${this.poster_sizes[3]}${item.poster_path}`" alt="Movie Poster">
    </div>
    <div class="title">
      Titolo: {{ item.title || item.name }}
    </div>
    <div class="original_title">
      Titolo originale: {{ item.original_title || item.original_name}}
    </div>
    <div class="language">
      Lingua originale:
      <span v-if="item.original_language === 'en'">
          <img src="/enflag.jpg" alt="flag image" class="flag">
      </span>
      <span v-else-if="item.original_language === 'it'">
          <img src="/itflag.png" alt="flag image" class="flag">
      </span>
      <span v-else-if="item.original_language === 'fr'">
          <img src="/frflag.jpg" alt="flag image" class="flag">
      </span>
      <span v-else>
        {{ item.original_language }}
      </span>
    </div>
    <div class="vote d-flex justify-content-center align-items-center">
      Voto: 
      <font-awesome-icon class="stars" :icon="['fas', 'star']" v-for="(n, i) in this.rating" :key="i"/>
      <font-awesome-icon class="stars" :icon="['far', 'star']" v-for="(n, i) in 5 - this.rating" :key="i"/>
    </div>
  </li>
</template>



<style lang="scss" scoped>
.flag{
    max-width: 30px;
}
.card_size{
    height: 100%;
    width: 342px;
}
.stars{
  color: gold;
}
</style>
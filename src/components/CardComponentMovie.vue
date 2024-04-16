<script>
  export default {
    props: ["movies"],
    data(){
        return{
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
  <div class="card card_size movies">
    <div class="poster">
      <img v-if="movies.poster_path !== null" :src="`${this.imagePath}${this.poster_sizes[3]}${movies.poster_path}`" alt="Movie Poster">
    </div>
    <div class="title">
      Titolo: {{ movies.title }}
    </div>
    <div class="original_title">
      Titolo originale: {{ movies.original_title }}
    </div>
    <div class="language">
      Lingua originale:
      <span v-if="movies.original_language === 'en'">
          <img src="/enflag.jpg" alt="flag image" class="flag">
      </span>
      <span v-else-if="movies.original_language === 'it'">
          <img src="/itflag.png" alt="flag image" class="flag">
      </span>
      <span v-else-if="movies.original_language === 'fr'">
          <img src="/frflag.jpg" alt="flag image" class="flag">
      </span>
      <span v-else>
        {{ movies.original_language }}
      </span>
    </div>
    <div class="vote">
      Voto: {{ movies.vote_average }}
    </div>
  </div>
</template>


<style lang="scss" scoped>
.flag{
    max-width: 30px;
}
.card_size{
    height: 100%;
    width: 342px;
}
</style>
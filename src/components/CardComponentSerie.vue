<script>
  export default {
    props: ["series"],
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
    <div class="card card_size series">
        <div class="poster">
            <img v-if="series.poster_path !== null" :src="`${this.imagePath}${this.poster_sizes[3]}${series.poster_path}`" alt="Serie Poster">
        </div>
        <div class="title">
          Titolo: {{ series.original_name }}
        </div>
        <div class="language">
          Lingua originale:
          <span v-if="series.original_language === 'en'">
              <img src="/enflag.jpg" alt="flag image" class="flag">
          </span>
          <span v-else-if="series.original_language === 'it'">
              <img src="/itflag.png" alt="flag image" class="flag">
          </span>
          <span v-else-if="series.original_language === 'fr'">
              <img src="/frflag.jpg" alt="flag image" class="flag">
          </span>
          <span v-else>
              {{ series.original_language }}
          </span>
        </div>
        <div class="vote">
          Voto: {{ series.vote_average }}
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
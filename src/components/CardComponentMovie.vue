<script>
  export default {
    props: ["movies"],
    data(){
        return{
        
        }
    }
  }
</script>


<template>
    <div class="card card_height movies">
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
.card_height{
    height: 100%;
}
</style>
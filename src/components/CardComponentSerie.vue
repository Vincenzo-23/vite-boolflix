<script>
  export default {
    props: ["series"],
    data(){
        return{
        
        }
    }
  }
</script>


<template>
    <div class="card card_height series">
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
.card_height{
    height: 100%;
}
</style>
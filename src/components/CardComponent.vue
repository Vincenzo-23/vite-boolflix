<script>
  export default {
    props: ["card"],
    data(){
        return{
        
        }
    }
  }
</script>


<template>
    <div class="card h-100">
        <div class="title">
          Titolo: {{ card.title }}
        </div>
        <div class="original_title">
          Titolo originale: {{ card.original_title }}
        </div>
        <div class="language">
          Lingua originale:
          <span v-if="card.original_language === 'en'">
              <img src="/enflag.jpg" alt="flag image" class="flag">
          </span>
          <span v-else-if="card.original_language === 'it'">
              <img src="/itflag.png" alt="flag image" class="flag">
          </span>
          <span v-else-if="card.original_language === 'fr'">
              <img src="/frflag.jpg" alt="flag image" class="flag">
          </span>
          <span v-else>
              {{ card.original_language }}
          </span>
        </div>
        <div class="vote">
          Voto: {{ card.vote_average }}
        </div>
    </div>
</template>


<style lang="scss" scoped>
.flag{
    max-width: 30px;
}
</style>
<script>
  export default {
    props: ["card"],
  }
</script>


<template>
  <div class="title">
    Titolo: {{ card.title }}
  </div>
  <div class="original_title">
    Titolo originale: {{ card.original_title }}
  </div>
  <div class="language">
    Lingua originale: {{ card.original_language }}
  </div>
  <div class="vote">
    Voto: {{ card.vote_average }}
  </div>
</template>


<style lang="scss" scoped>

</style>
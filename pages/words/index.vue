<template>
  <section class="container">
    <h1>Words</h1>
    <section class='word-list serif'>
      <div class="word-entry">
        <router-link to='words/using-nuxt'>Building this Site in Nuxt</router-link>
      </div>
      <div class='word-entry'>
        <router-link to='words/k-means'>Intro to Document Clustering with K-Means</router-link>
      </div>
    </section>
  </section>
</template>

<script>
  export default {
    asyncData ({ req }) {
      return
    }
  }
</script>

<style lang="sass" scoped>

  .word-list .word-entry
    font-size: 24px

</style>

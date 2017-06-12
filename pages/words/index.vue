<template>
  <section class="container">
    <h1>Words</h1>
    <div>      
      {{name}}
    </div>
    <section>
      Word list
      <router-link to='words/using-nuxt'>Building This Site in Nuxt</router-link>
    </section>
  </section>
</template>

<script>
  export default {
    asyncData ({ req }) {
      return {
        name: req ? 'server' : 'client'
      }
    }
  }
</script>

<template>
  <div>
    <div class='main-menu'>
      <router-link to='/'>Home</router-link>
      <router-link to='/about'>About</router-link>
      <router-link to='/words'>Words</router-link>
    </div>
    <nuxt/>
  </div>
</template>

<style lang='sass' scope>

  .main-menu
    padding: 25px 0
    display: flex
    justify-content: space-around

</style>

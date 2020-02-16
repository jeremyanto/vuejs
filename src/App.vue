<template>
  <div id="app" class="container center">

    <img alt="Vue logo" src="./assets/logo.png">
    <br>
    <router-link class="mr-5" to="/">accueil</router-link>
    <router-link to="/details">favories</router-link>

    <router-view></router-view>
  </div>
</template>

<script>


export default {
  name: 'App',
  components: {
  }
}
</script>

<style>
.center{
  text-align: center;
  margin-top: 2em;
}

body{
  background-color: whitesmoke;
}

h1, p{
  color: grey;
}
</style>

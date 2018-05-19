<template>
  <div id="app">
    <img src="./assets/logo.png">
    <h1>Twoj e-mail to {{ email.toLowerCase() }}</h1>
    
    <div v-if="!isAuthenticated || email.length < 5">
      <input type="email" v-model="email">
      <button @click="logIn()">Wchodzę</button>
    </div>
    
    <div v-else>
      Zalogowany jako {{email}}
      <button @click="logOut()">Wyloguj</button>
    </div>

    



    <h2>Essential Links</h2>
    <ul>
      <li><a href="https://vuejs.org" target="_blank">Core Docs</a></li>
      <li><a href="https://forum.vuejs.org" target="_blank">Forum</a></li>
      <li><a href="https://chat.vuejs.org" target="_blank">Community Chat</a></li>
      <li><a href="https://twitter.com/vuejs" target="_blank">Twitter</a></li>
    </ul>
    <h2>Ecosystem</h2>
    <ul>
      <li><a href="http://router.vuejs.org/" target="_blank">vue-router</a></li>
      <li><a href="http://vuex.vuejs.org/" target="_blank">vuex</a></li>
      <li><a href="http://vue-loader.vuejs.org/" target="_blank">vue-loader</a></li>
      <li><a href="https://github.com/vuejs/awesome-vue" target="_blank">awesome-vue</a></li>
    </ul>
  </div>
</template>

<script>
import "milligram";

export default {
  name: 'app',
  data() {
  return {
    email: '',
    isAuthenticated: false
  }
},
  methods: {
  alertMyEmail() {
    alert(this.email);
  }
},
  methods: {
    logIn() {
      this.isAuthenticated = true;
    },
    logOut() {
      this.isAuthenticated = false;
    }
  }
}
</script>

<style lang="scss">
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

h1, h2 {
  font-weight: normal;
}

ul {
  list-style-type: none;
  padding: 0;
}

li {
  display: inline-block;
  margin: 0 10px;
}

a {
  color: #42b983;
}
</style>

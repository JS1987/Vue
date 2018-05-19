<template>
  <div id="app">
    
    <h1>Witaj w systemie do zapisów na zajecia</h1>
    
    <div v-if="!isAuthenticated || email.length < 5">
      <input type="email" v-model="email">
      <button @click="logIn()">Wchodzę</button>
    </div>
    
    <div v-else>
      Zalogowany jako {{email}}
      <button @click="logOut()">Wyloguj</button>
    </div>

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

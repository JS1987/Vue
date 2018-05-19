<template>
  <div id="app">
    
    <h1>Witaj w systemie do zapisów na zajecia</h1>
    
    <div v-if="!authenticatedEmail">
      
      <login-form @login="logMeIn($event)"
      
                  :button-label="'W c h o d z ę!!!'"></login-form>

                  <login-form @login="logMeIn($event)"
                        :button-label="'Wejdz'"></login-form>
                  
                  <login-form @login="logMeIn($event)"
                        :button-label="'Wlec'"></login-form>
    </div>
    
    <div v-else>
      Zalogowany jako {{authenticatedEmail}}
      <button @click="logOut()">Wyloguj</button>
    </div>

  </div>
</template>

<script>
import "milligram";
import LoginForm from "./LoginForm";

export default {
  name: 'app',
  components: {LoginForm},
  data() {
  return {
    authenticatedEmail: ''
  }
},
  methods: {
  alertMyEmail() {
    alert(this.email);
  }
},
  methods: {
    logOut() {
      this.authenticatedEmail = '';
    },
    logMeIn(email) {
  this.authenticatedEmail = email;
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

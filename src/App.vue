<template>
  <div id="app">
    <div id="nav">
      <router-link to="/">Home</router-link> |
      <router-link to="/about" v-if="isLogged">About</router-link>
      <router-link v-if="!isLogged" to="/login"> Login </router-link> <span v-if="!isLogged">|</span> 
      <router-link v-if="!isLogged" to="/register"> Register </router-link> 
      <button id="logout" type="button" class="btn btn-link" @click="logout()" v-if="isLogged">
        Logout
      </button>
    </div>
    <router-view/>
  </div>
</template>

<script>
import { mapGetters } from 'vuex'

export default {
  computed: {
    ...mapGetters([
      'isLogged'
    ])
  },

  methods: {
    logout () {
      this.$store.dispatch('logout')
    }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

#nav {
  padding: 30px;
}

#nav a {
  font-weight: bold;
  color: #2c3e50;
}

#nav a.router-link-exact-active {
  color: #42b983;
}

#logout{
  position: absolute;
  right: 0;
  top: 0;
}
</style>

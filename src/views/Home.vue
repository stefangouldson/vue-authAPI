<template>
  <div class="home">
    <img alt="Vue logo" src="../assets/logo.png">
    <img alt="Laravel Logo" height="200px" src="https://upload.wikimedia.org/wikipedia/commons/thumb/9/9a/Laravel.svg/1200px-Laravel.svg.png">
    <HelloWorld msg="Simple API Login/Register using Vue and Laravel"/>
  </div>
</template>

<script>
// @ is an alias to /src
import HelloWorld from '@/components/HelloWorld.vue'

export default {
  name: 'Home',
  components: {
    HelloWorld
  }
}
</script>

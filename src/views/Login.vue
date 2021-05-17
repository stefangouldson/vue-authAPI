<template>
  <div>
    <h1>Login</h1>
    <form @submit.prevent="login">
        <div class="mb-3">
            <label for="email" class="form-label">Email address</label>
            <input class="form-control" id="email" type="email" name="email" v-model="email" placeholder="Enter your email address">
        </div>
        <div class="mb-3">
            <label for="password" class="form-label">Password</label>
            <input class="form-control" id="password" type="password" name="password" v-model="password" placeholder="Enter your password">
        </div>
      <button class="btn btn-success" type="submit">Login</button>
    </form>
  </div>
</template>

<script>
export default {
  data () {
    return {
      email: '',
      password: ''
    }
  },

  methods: {
    login () {
      this.$store
        .dispatch('login', {
          email: this.email,
          password: this.password
        })
        .then(() => {
          this.$router.push({ name: 'About' })
        })
        .catch(err => {
          console.log(err)
        })
    }
  }
}
</script>
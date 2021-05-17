<template>
  <div>
    <h1>Register</h1>
    <form @submit.prevent="register">
        <div class="mb-3">
            <label for="name" class="form-label">Name</label>
            <input class="form-control" id="name" type="text" name="name" v-model="name" placeholder="Enter your name">
        </div>
        <div class="mb-3">
            <label for="email" class="form-label">Email address</label>
            <input class="form-control" id="email" type="email" name="email" v-model="email" placeholder="Enter your email address">
        </div>
        <div class="mb-3">
            <label for="password" class="form-label">Password</label>
            <input class="form-control" id="password" type="password" name="password" v-model="password" placeholder="Create a password">
        </div>
      <button class="btn btn-success" type="submit">Register</button>
    </form>
  </div>
</template>

<script>
export default {
  data () {
    return {
      email: '',
      password: '',
      name: ''
    }
  },

  methods: {
    register () {
      this.$store
        .dispatch('register', {
          email: this.email,
          password: this.password,
          name: this.name
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
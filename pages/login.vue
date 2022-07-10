<template>
  <div>
    <form @submit.prevent="userLogin">
      <div>
        <label>Username</label>
        <input v-model="login.email" type="text">
      </div>
      <div>
        <label>Password</label>
        <input v-model="login.password" type="password">
      </div>
      <div>
        <button type="submit">
          Submit
        </button>
      </div>
    </form>
  </div>
</template>

<script>
export default {
  layout: 'empty',
  data () {
    return {
      login: {
        email: '',
        password: ''
      }
    }
  },
  methods: {
    userLogin () {
      this.$auth.loginWith('laravelJWT', { data: this.login }).then((res) => { }).catch(
        (err) => {
          console.log(err)
        })
    }
  }
}
</script>

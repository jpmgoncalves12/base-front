<template>
  <div>
    <h1>Default Layout</h1>
    <p>Logged With: {{ userName }}</p>
    <button @click="logout()">
      Logout
    </button>
    <Nuxt />
  </div>
</template>

<script>
export default {
  name: 'DefaultLayout',
  data () {
    return {
      userName: this.$auth.$state.user.data.name
    }
  },
  methods: {
    async logout () {
      await this.$auth.logout()
      this.$router.push('/login')
    }
  }
}
</script>

<template>
  <p>About</p>
</template>

<script>
export default {
  name: 'AboutPage',

  async asyncData ({ $axios }) {
    const data = {
      email: 'jpmgoncalves12+teste@gmail.com',
      password: 'Test1234'
    }

    const post = (await $axios.post('http://194.195.92.153:8080/auth/login', data))
    alert(post.data.data.token)
  }
}
</script>

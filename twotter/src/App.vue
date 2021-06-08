<template>
  <div id="app">
    {{ user.username }} - {{ firstName }}
  </div>
</template>

<script>
  export default {
    data() {
      return {
        followers: 0,
        user: {
          id: 1,
          username: 'realZachy',
          firstName: 'Zachary',
          lastName: 'Moseti',
          email: 'zachy@gmail.com',
          isAdmin: true
        }
      }
    },
    computed: {
      firstName() {
        return `${this.user.firstName} ${this.user.lastName}`
      }
    }
  }
</script>

<style scoped>
#app {
font-family: Avenir, Arial, Helvetica, sans-serif;
  display: flex;
  justify-content: center;
}
</style>
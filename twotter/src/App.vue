<template>
  <div id="app">
    {{ user.username }} - {{ firstName }} 
    <strong>followers: </strong>  {{ followers }} 
    <button @click="followUser">Follow</button>
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
    },
    methods: {
      followUser() {
        this.followers += 1;
      }
    }
  }
</script>

<style scoped>
#app {
font-family: Avenir, Arial, Helvetica, sans-serif;
  display: flex;
  flex-direction: column;
  text-align: center;
  margin-top: 20px;
}
button {
width: 100px;
  display: flex;
  justify-content: center;
  align-content: center;
  margin-left: 750px;
}
</style>
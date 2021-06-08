<template>
  <div id="app">
    {{ user.username }} - {{ fullName }} 
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
    watch: {
      followers(newFollowerCount,oldFollowerCount) {
          if(newFollowerCount > oldFollowerCount) {
            console.log('Zachary has gained a new follower!');
          }
      }
    },
    computed: {
      fullName() {
        return `${this.user.firstName} ${this.user.lastName}`
      }
    },
    methods: {
      followUser() {
        this.followers += 1;
      }
    },
    mounted() {
      this.followUser();
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

</style>
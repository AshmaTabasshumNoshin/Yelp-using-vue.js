<template>
  <div id="dashboard">
      <h1>You are an yelp user.</h1>
    <p v-for="(key, index) in email">
      <span v-if="key.email === checkLoginEmail ">Your email address: {{ key.email }}</span>
    </p>
  
  </div>
</template>

<script>

  export default {
    data(){
      return {
        checkLoginEmail: this.$store.state.userEmail
      }
    },
   computed: {
     email () {
       return !this.$store.getters.user ? false : this.$store.getters.user
     }
   },
    created () {
      this.$store.dispatch('fetchUser')
    }
  }
</script>

<style scoped>
  h1, p {
    text-align: center;
    font-family: cursive;
  }

  p {
    color: red;
    font-family: cursive;
  }
</style>
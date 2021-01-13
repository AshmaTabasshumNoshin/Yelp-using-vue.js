<template>
<div id="welcome">
    <h1>Welcome to yelp</h1>
    <p>Find the Best Businesses in Town</p> 
      <p>Browse Businesses by Category</p>
    </div>
 </template>
<script>
  export default {
    computed: {
      checkAuthUser() {
        return this.$store.getters.isAuthenticated;
      }
    }
  }
</script>

<style scoped>

#welcome 
  h1 {
    text-align: center;
     color: #df0404;
     font-family: cursive;
     font-weight: 200;
     font-size: 20px;
   line-height: 1.1em;
    
  }
p {
    text-align: center;
    font-family: cursive;
     font-weight: 200;
     font-size: 15px;
   line-height: 1.1em;}
    .cta a:hover,
  .cta a:active {
    background-color: #df0404;
    color: white;
  }
      

 
</style>
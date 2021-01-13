<template>
  <div id="Login">
      <h1>Log in to Yelp</h1>
<p> New to Yelp? Sign up</p>
<p>By logging in, you agree to Yelp’s Terms of Service and Privacy Policy.</p>
    <div class="Login-form">
      <form @submit.prevent="onSubmit">
        <div class="input">
          <label for="email">Mail</label>
          <input
                  type="email"
                  id="email"
                  v-model="email">
        </div>
        <div class="input">
          <label for="password">Password</label>
          <input
                  type="password"
                  id="password"
                  v-model="password">
        </div>
        
        <div class="LogIn">
          <button type="Log In">Log In</button>
          <p>New to Yelp? Sign up.</p>
        </div>
      </form>
    </div>
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
      onSubmit () {
        const formData = {
          email: this.email,
          password: this.password,
        }
        this.$store.dispatch('login', formData)
      }
    }
  }
</script>

<style scoped>
h1 {
    text-align: center;
    color: #df0404;
    font-family: cursive;
  }
 p {
    text-align: center;
    font-family: cursive;
  }

  .Login-form {
    position: center;
    width: 400px;
    margin: 30px auto ;
    border: 1px solid rgb(255, 255, 255);
    padding: 20px;
    box-shadow: 0 2px 3px rgb(255, 255, 255);

  }
  
  .input {
    margin: 10px auto;
  }

  .input label {
    display: block;
    color: #000000;
    margin-bottom: 6px;
  }
 .input.inline label {
    display: inline;
  }

 .input input {
    font: inherit;
    width: 100%;
    padding: 6px 12px;
    box-sizing: border-box;
    border: 1px solid rgb(0, 0, 0);
  }
  .input.inline input {
    width: auto;
  }

  .input input:focus {
    outline: none;
    border: 1px solid #df0404;
    background-color:rgb(255, 255, 255);
  }

  .Log In button {
    border: 1px solid #df0404;
    color: #df0404;
    padding: 10px 20px;
    font: inherit;
    cursor: pointer;
  }

  .Log In button:hover,
  .Log In button:active {
    background-color: #df0404;
    color: white;
  }

  .Log In button[disabled],
  .Log In button[disabled]:hover,
  .Log In button[disabled]:active {
    border: 1px solid rgb(255, 255, 255);
    background-color: transparent;
    color: rgb(255, 255, 255);
    cursor: not-allowed;
  }
</style>
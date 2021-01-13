<template>
  <div id="signup">
   <h1>Sign up For yelp</h1>
     <p>Connect with great local businesses</p>
          <div class="signup-form">
      <form @submit.prevent="onSubmit">
        <div class="input">
          <label for="Name">Name</label>
          <input
                  type="Name"
                  id="Name"
                  v-model="Name">
        </div>
        <div class="input">
          <label for="Email">Email</label>
          <input
                  type="Email"
                  id="Email"
                  v-model="Email">
        </div>
        <div class="input">
          <label for="ZIP Code">ZIP Code</label>
          <input
                  type="ZIP Code"
                  id="ZIP Code"
                  v-model="ZIPCode">
        </div>
        <div class="input">
          <label for="BirthDay">BirthDay</label>
          <input
                  type="BirthDay"
                  id="BirthDay"
                  v-model="BirthDay">
        </div>
        <div class="input">
          <label for="password">Password</label>
          <input
                  type="password"
                  id="password"
                  v-model="password">
        </div>
        <div class="input">
          <label for="confirm-password">Confirm Password</label>
          <input
                  type="password"
                  id="confirm-password"
                  v-model="confirmPassword">
        </div>
        <div class="input inline">
          <input type="checkbox" id="terms" v-model="terms">
          <label for="terms">Accept Terms of Use</label>
           <p>By accepting, you agree to Yelp’s Terms of Service and acknowledge Yelp’s Privacy Policy.</p>
        </div>
        <div class="submit">
          <button type="submit">Submit</button>
        </div>
        
      </form>
    </div>
  </div>
</template>

<script>
export default {
    data () {
      return {
        Name: '',
        Email: '',
        ZIPCode: '',
        BirthDay: '',
        password: '',
        confirmPassword: '',
        terms: false
      }
    },
    methods: {
      onSubmit () {
        const formData = {
          Name: this.Name,
          Email: this.Email,
          ZIPCode: this.ZIPCode,
          BirthDay: this.BirthDay,
          password: this.password,
          confirmPassword: this.confirmPassword,
          terms: this.terms
        }

        //Simple check if passwords matches
        if(this.password !== this.confirmPassword){
          alert("Passwords doesn't match!")
        }
        this.$store.dispatch('signup', formData)
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
  .signup-form {
    text-align: center;
    width: 400px;
    margin: 30px auto;
    border: 1px solid rgb(255, 255, 255);
    padding: 20px;
    box-shadow: 0 2px 3px rgb(255, 255, 255);
  }


  .input {
    margin: 10px auto;
  }

  .input label {
    display: block;
    color: rgb(0, 0, 0);
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
    background-color:rgb(255,255,255);
  }

  .input select {
    border: 1px solid rgb(255, 255, 255);
    font: inherit;
  }

  .hobbies button {
    border: 1px solid #df0404;
    background: #df0404;
    color: white;
    padding: 6px;
    font: inherit;
    cursor: pointer;
  }

  .hobbies button:hover,
  .hobbies button:active {
    background-color: #df0404;
  }

  .hobbies input {
    width: 90%;
  }

  .submit button {
    border: 1px solid #df0404;
    color: #df0404;
    padding: 10px 20px;
    font: inherit;
    cursor: pointer;
  }

  .submit button:hover,
  .submit button:active {
    background-color: #df0404;
    color: white;
  }

  .submit button[disabled],
  .submit button[disabled]:hover,
  .submit button[disabled]:active {
    border: 1px solid rgb(255, 255, 255);
    background-color: transparent;
    color: rgb(255, 255, 255);
    cursor: not-allowed;
  }
</style>
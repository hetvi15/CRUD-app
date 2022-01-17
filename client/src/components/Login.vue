<template>
<form @submit.prevent="getLogin">
<div>
   <img src="../assets/crud_app.png" alt="Logo"><br>
    <div class="form-control" :class="{invalid:loginform.usernameValidity === 'invalid'}">
        <input type="text" placeholder="Enter Username" v-model="loginform.username" required @blur="validateEmail"><br>
    </div>
    <p v-if="loginform.usernameValidity==='invalid'">Please enter a valid email</p>
    <br><br>

    <div class="form-control" :class="{invalid:loginform.passwordValidity === 'invalid'}">
         <input type="password" placeholder="Enter Password" v-model="loginform.password" required @blur="validatePassword"><br>
    </div>
     <p v-if="loginform.passwordValidity==='invalid'">A valid password should contain atleast eight characters,minimum one letter and one number</p>
    <br><br>
    <br>
    <button  v-on:click="getLogin"  style="color:whitesmoke" id="sub"><b>Login</b></button>
   <br><br>
   <router-link to="SignUp.vue">
       <button type="button"  id="SignUp" >Not a Member? Sign Up</button>
   </router-link>
    <hr>
    <router-view></router-view>
   </div>
</form>
</template>

<script>
export default {
  name: 'Login',
  data () {
    return {
      loginform: {
        username: '',
        password: '',
        usernameValidity: '',
        passwordValidity: ''
      }

    }
  },
  methods: {
    getLogin () {
      console.log(this.loginform.username + this.loginform.password +
      this.loginform.usernameValidity +
      this.loginform.passwordValidity)
    },
    validateEmail () {
      // eslint-disable-next-line no-useless-escape
      if (/^\w+([\.-]?\w+)*@\w+([\.-]?\w+)*(\.\w{2,3})+$/.test(this.loginform.username)) {
        this.loginform.usernameValidity = 'valid'
      } else {
        this.loginform.usernameValidity = 'invalid'
      }
    },
    validatePassword () {
    // eslint-disable-next-line no-useless-escape
      if (/^(?=.*[A-Za-z])(?=.*\d)[A-Za-z\d]{8,}$/.test(this.loginform.password)) {
        this.loginform.passwordValidity = 'valid'
      } else {
        this.loginform.passwordValidity = 'invalid'
      }
    }
  }
}

</script>

<style>
template{
    align-content: center;
}
p{
    color:red;
    font-size: small;
}
h2{
    font-weight: 800;
}
.form-control.invalid input {
    border-color: red;
}
/* Full-width inputs */
input[type=text], input[type=password] {
  width: 50%;
  padding: 12px 20px;
  display: inline-block;
  border: 1px solid #ccc;
  box-sizing: border-box;
}

/* Set a style for all buttons */
#sub{
  background-color:#191970;
  color: #111111;
  padding: 15px 20px;
  margin: 20px 0;

  cursor: pointer;
  width: 50%;
}
#SignUp{
    width:20%;
    background-color:#191970;
  color: #111111;
  padding: 15px 20px;
  margin: 20px 0;
  color:whitesmoke;
}

/* Add a hover effect for buttons */
button:hover {
  opacity: 0.8;
}

img.avatar {
  width: 15%;
  height: 15%
}

/* The "Forgot password" text */
span.psw {
  float:center;
  padding-top: 16px;
  margin-left:20%;
}

</style>

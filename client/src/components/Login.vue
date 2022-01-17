
/* eslint-disable */
<template>
<div>
   <img src="../assets/crud_app.png" alt="Logo"><br>
    <input type="text" placeholder="Enter Username" v-model="loginform.username" required><br>
    <input type="password" placeholder="Enter Password" v-model="loginform.password" required><br>
    <button  v-on:click="getLogin"  style="color:whitesmoke" id="sub"><b>Login</b></button>
     <br>
     <button type="button"  id="SignUp" >Not a Member? Sign Up</button>

    <span class="psw"> <a href="recover.html">Forgot password?</a></span>
</div>
</template>

<script>
export default {
  name: 'Login',
  data () {
    return {
      loginform: {
        username: '',
        password: ''
      },
      logo: './assets/crud-app.png'

    }
  },
  methods: {
    getLogin () {
      console.log(this.loginform.username + this.loginform.password)
    }
  }

}
</script>

<style>
template{
    align-content: center;
}
h2{
    font-weight: 800;
}
/* Full-width inputs */
input[type=text], input[type=password] {
  width: 50%;
  padding: 12px 20px;
  margin: 8px 0;
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

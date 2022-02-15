<template>
  <div class="login"     >
   <img class="imglog" src="../assets/img/Rsta.png" alt="">
    <h1 class="log">Log in</h1>
    <div class="register">
      <input type="text"  v-model="email" placeholder="Email" name="" id="" required />
      <input type="text"  v-model="password" placeholder="Password"  required />
      <button class="submit" v-on:click="login">LogIn</button>
      <h5 class="sign"><router-link to="/signup">Sign Up</router-link></h5>
    </div>

  </div>

</template>


<script>
import axios from "axios";

export default {
  name: "login",
  data() {
    return {
      email: '',
      password: '',
    };
  },
  methods: {
    async login() {
      let result = await axios.get(
          'http://localhost:3000/users?email=${this.email}&{this.password}'
      );
      if (result.status ===200 && result.data.length > 0)
      {
        localStorage.setItem("user-info",JSON.stringify(result.data[0]));
         await this.$router.push({name: 'Home'});
      }
    },
  },
  mounted() {
    let user = localStorage.getItem('user-info');
    if (user)
    {
      this.$router.push({name: 'Home'})
    }
  }
}
</script>

<style scoped>
.imglog{
  width: 100px;
  display: block;
  margin-right: auto;
  margin-left: auto;
}
.log{
  text-align: center;
  color: #2c3e50;
  font-size: larger;
  font-family: cursive;
  font-weight: bolder;
}
.register input{
  width: 300px;
  height: 40px;
  border: 1px solid skyblue;
  padding-left: 20px;
  display: block;
  margin-bottom: 30px;
  margin-right: auto;
  margin-left: auto;
  cursor: pointer;
}
.submit{
  background-color: skyblue;
  display: block;
  margin-left: auto;
  margin-right: auto;
  width: 330px;
  height: 40px;
  border: 1px solid skyblue;
  cursor: pointer;
  color: white;
}
.sign{
  display: block;
  cursor: pointer;
  margin-left: auto;
  margin-right: auto;
  text-align: center;
}

</style>

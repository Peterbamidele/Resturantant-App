<template>
  <div class="sign">
    <img class="logo" src="../assets/img/Rsta.png"  alt="">
    <h1>Sign Up</h1>
    <div class="register">
      <input type="text"  v-model="name" placeholder="Name" required  />
      <input type="text" v-model="email" placeholder="Email" Unique  required />
      <input type="text" v-model="password"  placeholder="password" required mdi />
      <button v-on:click="signUp"> Sign Up</button>
      <p class="sig">
        <router-link to="/login">Login</router-link>
      </p>
    </div>
  </div>
</template>

<script>
import axios from 'axios'
export default {
  name: "signUp",
  data(){
    return{
      name:'',
      email:'',
      password:'',
    }
  },
  methods:{
    async signUp(){
      console.warn("signUp",this.name,this.email,this.password)
      let result = await axios.post("http://localhost:3000/users", {
        name: this.name,
        email: this.email,
        password: this.password
      });
      console.warn(result);
      if (result.status === 201){
        // alert("signUp done")
        localStorage.setItem("user-info",JSON.stringify(result.data))
        await this.$router.push({name: 'Home'})
      }

    }
  },
  mounted() {
   let users = localStorage.getItem( 'users-info' );
   if (users){
     this.$router.push({name:'Home'})
   }
  }

}
</script>

<style scoped>
.sign h1{
  color: #2c3e50;
  font-size: large;
  font-weight: bolder;
  font-family: cursive;
  text-align: center;
}
.logo{
  width: 100px;
  display: block;
  margin-left: auto;
  margin-right: auto;
}
.register input{
  width: 300px;
  height: 40px;
  padding-left: 20px;
  display: block;
  margin-bottom: 30px;
  margin-right: auto;
  margin-left: auto;
  border: 1px solid skyblue;
  cursor: pointer;
}
.register button{
  width: 320px;
  height: 40px;
  border: 1px solid skyblue;
  background:skyblue;
  color: aliceblue;
  cursor: pointer;
  display: block;
  margin-right: auto;
  margin-left: auto;
}
.sig{
  text-align: center;
  font-size: medium;
  color: #2c3e50;
  cursor: pointer;
}

</style>

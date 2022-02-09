<template>
  <div class="sign">
    <img class="logo" src="../assets/img/Rsta.png"  alt="">
    <h1>Sign Up</h1>
    <div class="register">
      <input type="text" placeholder="Name" required  />
      <input type="text" placeholder="Email" Unique  required />
      <input type="text" placeholder="password" required mdi />
      <button> Sign Up</button>
    </div>
  </div>
</template>

<script>
export default {
  name: "SignUp"
}
</script>

<style scoped>
.sign h1{
  color: #2c3e50;
}
.logo{
  width: 100px;
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

}

</style>

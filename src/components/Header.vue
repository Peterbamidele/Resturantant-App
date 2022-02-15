<template>
  <div class="nav">
    <a href="home.vue">Home</a>
    <a href="home.vue">Add Restaurant</a>
    <a href="home.vue">Update Restaurant</a>
    <a href="login.vue">Logout</a>

  </div>
</template>

<script>
export default {
  name: "Header"
}
</script>

<style scoped>
.nav{
  background-color: #2c3e50;
  overflow: hidden;
}
.nav a{
  float: left;
  color: white;
  text-align: center;
  padding: 16px 14px;
  text-decoration: none;
  font-size: 16px;
  margin-right: 4px;
}
.nav a:hover{
  background-color: bisque;
  color: #222;
}
</style>

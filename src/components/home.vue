<template>
  <div>
  <h1 style="text-align: center" >Welcome to our home page</h1>
  </div>
</template>

<script>
export default {
  name: "home",
  mounted() {
    let users = localStorage.getItem( 'users-info' );
    if (users){
      this.$router.push({name:'SignUp'})
    }
  }
}
</script>

<style scoped>

</style>

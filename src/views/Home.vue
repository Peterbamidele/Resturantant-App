<template>
<div>
<Header/>
<home/>
</div>
</template>

<script>
import home from "@/components/home";
import Header from "@/components/Header";

export default {
  name: "Home",
  components:{
    home,Header,
  }
}
</script>

<style scoped>

</style>

<template>

  <div class="home">
    <img class ="vulo" alt="Vue logo" src="../assets/WORLD.png">
  </div>
  <nav>
   <router-link class="but" to="/login">LOGIN </router-link>
   </nav>
   
</template>

<script>
// @ is an alias to /src


export default {
  name: 'Home',

}

</script>

<style scoped>

.vulo{
  padding-top: 10px !important;
}

.but {
  font-size: 35px !important;
  font-weight: bold;
  color: black;
 
}

a:hover {
  color: yellow !important;
}

.but:hover {
  color: yellow !important;
}



</style>

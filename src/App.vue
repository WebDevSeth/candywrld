<template>
  <div id="nav">
    
   
  </div>
  <router-view/>
  
</template>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}


*{
  background-color: #FF66C4 !important;
}

#nav {
  padding: 30px;
}

#nav a {
  font-weight: bold;
  color: black;
}

#nav a.router-link-exact-active {
  color: #5CE1E6;
}

#app {
  font-family: Roboto, Helvetica, Arial, sans-serif;
}



</style>

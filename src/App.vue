<template>
  <div id="app">
   <Navbar />
   <div class="content">
     <Categorias />
     <Productos />
   </div>
  </div>
</template>

<script>
import Navbar from "./components/Navbar"
import Categorias from "./components/Categorias"
import Productos from "./components/Productos"

export default {
  name: 'App',
  components: {
    Navbar, Categorias, Productos
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

.content{
  display: flex;
}

</style>

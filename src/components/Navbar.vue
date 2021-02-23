<template>
    <div class="navbar-here">
  <b-navbar toggleable="lg" type="dark" variant="white">
    <b-navbar-brand href="#">
        <img class="petlogo" src="../assets/logo-petlove.png" alt="">
    </b-navbar-brand>

    <b-navbar-toggle class="btn-toggle" target="nav-collapse"></b-navbar-toggle>

    <b-collapse id="nav-collapse" is-nav>

      <!-- Right aligned nav items -->
      <b-navbar-nav class="ml-auto">
        <b-nav-form>
          <b-form-input id="input-search" size="md" class="mr-sm-2" placeholder="Buscar pets"></b-form-input>
          <b-button id="btn-search" size="md" class="my-2 my-sm-0" type="submit">Buscar</b-button>
         
        </b-nav-form>

        
      </b-navbar-nav>
    </b-collapse>
  </b-navbar>
</div>
</template>

<script>

</script>

<style scoped>
.petlogo{
    width: 100px;
}
.navbar-here{
    color: #333;
    margin-top: -60px;
    -webkit-box-shadow: 0px 3px 5px 0px rgba(0,0,0,0.25);
    -moz-box-shadow: 0px 3px 5px 0px rgba(0,0,0,0.25);
    box-shadow: 0px 3px 5px 0px rgba(0,0,0,0.25);
}
#input-search{
    width: 500px;
}
.btn-toggle,
#btn-search{
    color: rgb(255, 255, 255)!important;
    background: rgb(254, 118, 118)!important;
}

</style>
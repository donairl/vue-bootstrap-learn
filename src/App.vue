<template>

<b-container fluid>
 <b-navbar toggleable="lg" type="dark" variant="info" class="wide">
  <b-navbar-brand href="#">Demo Vue</b-navbar-brand>

    <b-navbar-toggle target="nav-collapse"></b-navbar-toggle>

    <b-collapse id="nav-collapse" is-nav>
      <b-navbar-nav>
        <b-nav-item to="/">Home</b-nav-item>
        <b-nav-item to="/about">About</b-nav-item>
      </b-navbar-nav>
    </b-collapse>  

 </b-navbar>      
  

  <b-row>
     <b-col>
       <b-nav vertical class="w-75">
        <b-nav-item active to="/book">Book</b-nav-item>
        <b-nav-item active to="/user">User</b-nav-item>
        <b-nav-item to="/login">Login</b-nav-item>
        <b-nav-item>List</b-nav-item>
        <b-nav-item disabled>Disabled</b-nav-item>
      </b-nav>
     </b-col>
     <b-col cols="10"><router-view/></b-col>
    
  </b-row>
</b-container>
 
  
 
</template>

<style>


#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

#nav {
  padding: 30px;
}

.wide{
  margin-left:-15px;
  margin-right:-15px;
}

#nav a {
  font-weight: bold;
  color: #2c3e50;
}

#nav a.router-link-exact-active {
  color: #42b983;
}
</style>

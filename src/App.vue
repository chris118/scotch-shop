<template>
  <div id="app">
    <nav id="nav">
      <ul>
        <!-- Navigation Links -->
        <li><router-link to="/">Home</router-link></li>
        <li><router-link to="/admin">Admin</router-link></li>
        <li><router-link to="/cart">Cart</router-link></li>
      </ul>
    </nav>
    <br>
    <router-view/>
  </div>
</template>

<script>
export default {
  name: 'app'
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

#nav{
  width: 100%;
  height: 45px;
  background-color: #000000;
}

#nav li{
  display: inline-block;
  width: 120px;
  height: 45px;
  line-height: 45px;
  float: left;
}

#nav li a{
  text-decoration: none;
  color: white;
  display: block;
  text-align: center;
  font-size: 20px;
}

#nav li a:hover{
  background-color: #338ce6;
}
</style>

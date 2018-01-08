<template>
  <div>
    <div class="admin-new">
      <div class="container">
        <div class="col-lg-3 col-md-3 col-sm-12 col-xs-12">
          <ul class="admin-menu">
            <!-- Links are to sibling routes -->
            <li><router-link to="/admin">View Products</router-link></li>
            <li><router-link to="/admin/new">New Product</router-link></li>
          </ul>
        </div>
        <!-- Outlet for children routes -->
        <router-view></router-view>
      </div>
    </div>
  </div>
</template>

<script>
  export default {
    name: 'home',
    data () {
      return {
        msg: 'Welcome to the Admin Page'
      }
    }
  }
</script>

<style>
  .admin-menu {
    list-style:none;
    padding: 0px;
    width: 150px;
    height: auto;
    float: left;
    background: orange;
  }


  .admin-menu li{
    width: 100%;
    height: auto;
    line-height: 45px;
    border-top: white 2px solid;
    float: left;
  }

  .admin-menu li a{
    text-decoration: none;
    color: black;
    display: block;
    text-align: center;
    font-size: 20px;
  }

  .admin-menu li a:hover{
    background-color: #338ce6;
  }
</style>

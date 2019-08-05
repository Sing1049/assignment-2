<template>
  <div class="card text-center" id="app">
    <div class="card-header">
      <ul class="nav nav-tabs card-header-tabs">
        <li class="nav-item">
          <router-link class="nav-link" to="/Signup">Signup</router-link>
        </li>
        <li class="nav-item">
          <router-link class="nav-link" to="/Dashboard">Dashboard</router-link>
        </li>
      </ul>
    </div>

    <router-view />

    <div class="card-footer">
      <p style="text-align:right;padding:10px;">
        &copy; Copyright |
        <a href="mailto:sing1049@algonquinlive.com">Gurjeet Singh</a>
      </p>
    </div>
  </div>
</template>
<script>
import "bootstrap/dist/css/bootstrap.css";
import "bootstrap-vue/dist/bootstrap-vue.css";
export default {};
</script>
<style>
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
#nav {
  padding: 30px;
}

#nav a {
  font-weight: bold;
  color: #2c3e50;
}

#nav a.router-link-exact-active {
  color: #42b983;
}
</style>

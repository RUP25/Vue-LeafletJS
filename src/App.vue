<template>
  <div id="app">
    
    <Navbar />
    <nav class="main-nav">
      <div class="logo"></div>
      <Burger />
    </nav>

    <Sidebar>
      <ul class="sidebar-panel-nav">
        <li><a href="#home">Home</a></li>
        <li><a href="#about">About</a></li>
        <li><a href="#contact">Contact</a></li>
        <li>
          <a
            ><label class="container"
              >City
              <input
                type="checkbox"
                id="city"
                name="city"
                value="City"
              /> </label
          ></a>
        </li>
      </ul>
    </Sidebar>
    <Map />
  </div>
</template>

<script>
import Navbar from "./components/Navbar.vue";
import Burger from "./components/Menu/Burger.vue";
import Sidebar from "./components/Menu/Sidebar.vue";
import Map from "./components/map.vue";

export default {
  name: "App",
  components: {
    Map,
    Navbar,
    Burger,
    Sidebar,
  }
};
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

html {
  height: 100%;
  overflow: hidden;
}

body {
  border: 0;
  margin: 0;
  padding: 0;
  font-family: "Lato";
  height: 100%;
  background: rgb(255, 255, 255);
  background: linear-gradient(
    45deg,
    rgb(255, 255, 255) 0%,
    rgb(255, 255, 255) 48%,
    rgb(255, 255, 255) 100%
  );
}

.logo {
  align-self: center;
  color: #fff;
  font-weight: bold;
  font-family: "Lato";
}

.main-nav {
  display: flex;
  justify-content: space-between;
  padding: 0.5rem 0.8rem;
}

ul.sidebar-panel-nav {
  list-style-type: none;
}

ul.sidebar-panel-nav > li > a {
  color: #fff;
  text-decoration: none;
  font-size: 1.5rem;
  display: block;
  padding-bottom: 0.5em;
}
</style>

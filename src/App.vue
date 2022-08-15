<template>
  <div id="app">
    <div id="wrapper">
      <div id="navbar">
        <ul id="navright">
          <router-link to="/" style="justify-content: flex-end">Home</router-link> |
          <router-link to="/about">About</router-link> |
          <router-link to="/my-work">My Work</router-link> |
          <a href="./resume.pdf" download="Nick Hass Resume">Resume</a>
        </ul>
      </div>
      <router-view />
      <div class="footer-container">
        <div class="footer">
          <!-- Add font awesome icons -->
          <a href="https://www.linkedin.com/in/nick-hass-725664139/" class="fa fa-linkedin"></a>
          <a href="https://github.com/nickhass3" class="fa fa-github"></a>
          <a href="https://medium.com/@nickhass3" class="fa fa-medium"></a>
        </div>
      </div>
    </div>
  </div>
</template>

<style>
html, body, #app {
  height: 100%;
  display: flex;
  flex-direction: column;
}

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  display: flex;
  flex-direction: column;
  min-height: 100vh;
}

#wrapper {
  /*flex: 1 0 auto;*/
  min-height: 100%;
  display: flex;
  flex-direction: column;
}

#navbar {
  padding: 30px;
  font-size: 1.5em;
  /*margin-left: auto; !*This pushes nav to the right*!*/
}

#navbar a {
  font-weight: bold;
  color: #2c3e50;
  text-decoration: none;
}

#navbar a.router-link-exact-active {
  color: #900c3f;
}

#navbar a:hover {
  color: #d5a4b7;
}

.footer-container{
  margin-top: auto;
}

.footer {
  background-color: #efefef;
  /*flex: 0 0 50px;!*or just height:50px;*!*/
  margin-top: auto;
  padding: 50px;
}

.footer a {
  color: #900c3f;
  font-size: 25px;
  padding: 0 50px;
  text-decoration: none;
}

.footer a:hover {
  color: #d5a4b7;
}

</style>

<script>
import axios from "axios";
export default {
  created() {
    console.log('hello');
    this.getItems();
  },
  methods: {
    async getItems() {
      try {
        let response = await axios.get("/api/items");
        this.items = response.data;
        return true;
      } catch (error) {
        console.log(error);
      }
    }
  }
}
</script>
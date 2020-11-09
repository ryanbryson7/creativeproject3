<template>
  <div id="app">
    <div class="page-container">
      <div id="nav">
        <router-link to="/">Home</router-link> |
        <router-link to="/browse">Browse</router-link> |
        <router-link to="/playlist">Playlist</router-link>
      </div>
      <router-view/>
    </div>
    <footer>
      <a href="https://github.com/ryanbryson7/creativeproject3">Github Repository</a>
    </footer>
  </div>
</template>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

.page-container {
  min-height: calc(100vh - 75px);
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

footer {
  height: 60px;
  align-items: center;
  text-align: center;
  padding-top: 40px;
}
</style>

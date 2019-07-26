<template>
  <div class="app">
    <router-view />
  </div>
</template>

<style>
.app {
  font-family: "나눔바른고딕";
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
.shadow {
  box-shadow: 5px 10px 10px rgba(0, 0, 0, 0.03);
}
h2 {
  font-weight: 300;
  font-size: 2rem;
}
</style>

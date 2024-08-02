<template>
  <nav>
    <router-link to="/">Home</router-link>
    <router-link to="/about">About</router-link>
    <router-link to="/test">Test</router-link>
    <router-link to="/basic">3.콤포넌트 (기본)</router-link>
    <router-link to="/deep">8.콤포넌트 (심화)</router-link>
    <router-link to="/member">회원가입</router-link>
  </nav>
  <router-view/>
</template>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

nav {
  padding: 5px 40px;
  display: flex;
  flex-direction: column;
  position: absolute;
  top: 10px;
  right: 10px;
  border-left: 1px solid #ccc;
  box-shadow: 5px 5px 5px 5px#ccc;
  background-color: #fff;
  border-radius: 5px;
  z-index: 1000;
}

nav a {
  font-weight: bold;
  font-size: 12px;
  color: #2c3e50;
  padding: 10px 20px;
  border: 1px solid #ccc;
  border-radius: 5px;
  margin-bottom: 10px;
  box-shadow: 3px 3px 3px 1px#ccc;
  transition: all 0.3s ease-in-out;
}
nav a:hover{
  background-color: #3d3d3d;
  color: #ffffff;
}

nav a.router-link-exact-active {
  color: #ffffff;
  background-color: #3d3d3d;
}
@media screen and (max-width: 800px){
  nav{
    top: initial;
    left: initial;
    right: initial;
    bottom: 0;
    width: 100%;
    flex-direction: row;
  }
  nav a{
    width: 60px;
    height: 20px;
    line-height: 20px;
    font-size: 12px;
  }
}
</style>

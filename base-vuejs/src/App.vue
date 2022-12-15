<template>
  <div id="app">
        <userProfile/>
  </div>
</template>

<script>
 import userProfile from "./components/UserProfile";

export default {
  name: 'App',
  components :{userProfile}
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  display: flex;
 text-align: center;
 flex-direction: column;
}
</style>

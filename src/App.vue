<template>
  <div id="app">
    <remoteJobs />
  </div>
</template>
<script>
  import remoteJobs from "./components/RemoteJobs.vue";
  export default {
    name: 'App',
    components: {
      remoteJobs
    }
  }
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
</style>

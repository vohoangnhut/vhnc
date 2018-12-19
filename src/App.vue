<template>
  <div id="app">
    <HelloWorld :msg='imsg'/>
  </div>
</template>

<script>
import HelloWorld from './components/index.vue'

export default {
  name: 'app',
  data() {
      return {
        imsg : "",
      }
  },
  components: {
    HelloWorld
  },

  methods: {

    getParams(url){
      var params = {};
      var parser = document.createElement('a');
      parser.href = url;
      var query = parser.search.substring(1);
      var vars = query.split('&');
      for (var i = 0; i < vars.length; i++) {
        var pair = vars[i].split('=');
        params[pair[0]] = decodeURIComponent(pair[1]);
      }
      return params;
    }
  },

  created() {
    var url = this.getParams(window.location.href);
    if(url && url.code)
    this.imsg = url.code;
  },
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
</style>

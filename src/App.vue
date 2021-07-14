<template>
 <div class="container">

   <h1 class="header">Line-Up 11 App</h1>

   <app-add-player style="background-color: #2C8300">

   </app-add-player>
   <br><br>
   <app-starting></app-starting>

 </div>
</template>

<script>

    import AddPlayer from "./components/AddPlayer";
    import Starting from "./components/Starting";

    export default {
      name: 'app',
      data () {
        return {

        }
      },
      components : {
        appAddPlayer : AddPlayer,
        appStarting : Starting,
      },

    }
</script>

<style>

.container{
  width: 1192px;
  margin-left: auto;
  margin-right: auto;
  text-align: center;
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
}

.header{
  color: #a71919;
  margin-top: 50px;
  margin-bottom: 25px;
}
/*#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

h1, h2 {
  font-weight: normal;
}

ul {
  list-style-type: none;
  padding: 0;
}

li {
  display: inline-block;
  margin: 0 10px;
}

a {
  color: #42b983;
}*/
</style>

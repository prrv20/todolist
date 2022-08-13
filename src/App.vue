<template>
  <div id="app">
    <h1>{{ titulo }}</h1>
    <form class="form" action="" >
      <label for="">Tarea:</label>
      <input v-model="nuevaTarea" type="text" name="tarea" id="tarea">
      <button @click.prevent="agregarTarea">Agregar Tarea</button>
      
    </form>
    <h3>Lista</h3>
    <div class="lista">
      <ul>
          <li v-for="(tarea, i) in tareas" :key="i">{{i}} : {{ tarea }}</li>
      </ul>
    </div>
  </div>
  
</template>

<script>

export default {
  name: 'App',
  data(){
    return{
      titulo: 'Crea una Nueva Tarea',
      nuevaTarea:'',
      tareas: []
    } 
  },
  methods:{
    agregarTarea(){
      this.tareas.push(this.nuevaTarea)
      this.nuevaTarea = ''
    }
  },
  components: {
    //HelloWorld
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  font-size: 1.2em;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  
  color: #2c3e50;
  margin-top: 1em;
  text-align: center;
}

.lista{
  text-align: left;
  margin: 2em auto;
  width: 20%;
}
#tarea{
 margin: 0 1em;
}
label{
  font-size: 1.2em;
}
li{
  padding: .3em 0;
}

</style>

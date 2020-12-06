<template>
  <div class='container mt-5'>

      <h1>{{ title }}</h1>
        <p>
            {{ profesores.nombre }}
        </p>

        <input type="text" class='form-control mt-4' v-model='nuevaTarea' v-on:keyup.enter='agregarTarea'>
        <button 
            class='btn btn-dark mt-2'
            v-on:click='agregarTarea'>
            Agregar tarea compa
        </button>

        <div class='mt-3' v-for='(item, index) of tareas' :key='item.id'>
            
            <div
            :class = "[item.estado ? 'alert-primary' : 'alert-warning']" 
            class="alert" 
            role="alert">
                
                <div class="d-flex justify-content-between align-items-center">
                    
                    <div>
                        {{ item.nombre }}
                    </div>
                    <div>
                        {{ item.estado }}
                    </div>
                    
                    <div>
                        <button class='btn btn-primary' @click='editarTarea(index)'>oquei</button>
                        <button class='btn btn-danger' @click='eliminarTarea(index)'>delete</button>
                    </div>                   
                </div>
            </div>
        </div>

    </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  props: {
    msg: String,
    title: String
  },
   data() {
        return {
            sesion: 5,
            profesores: {
                'nombre': 'Yasar José',
                'ciclo': '3'
            },
            nuevaTarea: '',
            tareas: []
        }
    },
    methods: {
        agregarTarea: function(){
            this.tareas.push({
                nombre: this.nuevaTarea,
                estado: false
            });

            this.nuevaTarea = '';
            localStorage.setItem('tareas-vue', JSON.stringify(this.tareas));
        },

        editarTarea( index ){
            this.tareas[index].estado = !this.tareas[index].estado;
            // localStorage.setItem('tareas-vue', JSON.stringify(this.tareas));
        },

        eliminarTarea: function(index){
            this.tareas.splice(index, 1);
            localStorage.setItem('tareas-vue', JSON.stringify(this.tareas));
        }

    },
    computed: {

    },
    created: function () {
        let dataDB = JSON.parse(localStorage.getItem('tareas-vue'));
        if (dataDB === null) {
            this.tasks = [];
        } else {
            this.tasks = dataDB;
        }

    }


}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
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
}
</style>

<template>
  <div id="app">

    <Carousel/>

    <!-- Noticias -->
    <section class="container-fluid">
      <hr>
      <page-news title="Sección de Noticias"/>
    </section>

    <section class="container-fluid">
      <hr>
      <h2 class="text-center">Equipo de trabajo</h2>
      <div class="card-deck">
        <div class="card m-1" v-for="(item, index) of team" v-bind:key="index">
          <team-card :member="item"></team-card>
        </div>
      </div>
    </section>


    <PruebaAxios/>



    <Probemos title="Welcome to Your Test Part of App"/>
  </div>
</template>

<script>

import Probemos from './components/Probemos.vue';
import Carousel from './components/Carousel.vue';
import TeamCard from './components/TeamCard.vue';
import PageNews from './components/PageNews.vue';
import PruebaAxios from './components/PruebaAxios.vue';

export default {
  name: 'App',
  components: {
    Probemos,
    Carousel,
    TeamCard,
    PruebaAxios,
    PageNews
  },
   data() {
      return {
        title: "Vue example",
        team: [
            {
                codigo : 1 ,
                nombre : "Wolfgang Santamaría" ,
                descripcion : "Ingeniero, Músico y sobre apasionado a los videojuegos." ,
                rol : "Scrum Master" ,
                image : "images/wolf.jpeg"
            },
            {
                codigo : 2 ,
                nombre : "Yasar José Cure" ,
                descripcion : "Estudiante de Ingeniería de Sistemas. Me gusta la comida, jugar fútbol y los videojuegos, pero eso cuando hay tiempo." ,
                rol : "Desarrollador backend" ,
                image : "images/yaser.jpeg"
            },
            {
                codigo : 3 ,
                nombre : "Geraldine Claros" ,
                descripcion : "Habilidades y competencias en ciencias físicas, matemáticas y en diversos lenguajes de programación." ,
                rol : "Desarrollador frontend" ,
                image : "images/geral.jpeg"
            },
            {
                codigo : 4,
                nombre : "Jason Roberto Camargo" ,
                descripcion : "Apasionado por el desarrollo de software y la tecnologia. Amante a la velocidad. Biker " ,
                rol : "Documentador" ,
                image : "images/jason.jpeg"
            },
            {
                codigo : 5 ,
                nombre : "Jaime Andrés Bravo" ,
                descripcion : "Ingeniero mecanico, baterista, ciclista, y exfutbolista. Incursionando en el desarrollo de aplicaciones. Con experiencia en el montaje de calderas" ,
                rol : "Diseñador Gráfico" ,
                image : "images/andres.jpeg"
            }
        ]
      }
    }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  /* text-align: center; */
  color: #2c3e50;
  margin-top: 60px;
}
</style>

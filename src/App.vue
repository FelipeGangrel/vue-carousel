<template>
  <div id="app">
    <carousel>
      <template v-for="slide of slides">
        <carousel-slide>
          <div style="position: absolute; left: 0; right: 0; top: 50%; text-align: center; color: #fff; font-size: 30px;">{{slide.titulo}}</div>
          <img :src="slide.imagem" width="100%">
        </carousel-slide>
      </template>
    </carousel>
  </div>
</template>

<script>
  import Carousel from './components/Carousel.vue';
  import CarouselSlide from './components/CarouselSlide.vue';
  export default {
    name: 'app',
    data() {
      return {
        slides: [{
          imagem: "http://lorempicsum.com/futurama/627/300/1",
          titulo: 'Título aqui'
        }, {
          imagem: "http://lorempicsum.com/futurama/627/300/2",
          titulo: 'Título aqui'
        }, {
          imagem: "http://lorempicsum.com/futurama/627/300/3",
          titulo: 'Título aqui'
        }, {
          imagem: "http://lorempicsum.com/futurama/627/300/4",
          titulo: 'Título aqui'
        }, {
          imagem: "http://lorempicsum.com/futurama/627/300/5",
          titulo: 'Título aqui'
        }, {
          imagem: "http://lorempicsum.com/futurama/627/300/6",
          titulo: 'Título aqui'
        }, {
          imagem: "http://lorempicsum.com/futurama/627/300/7",
          titulo: 'Título aqui'
        }]
      }
    },
    components: {
      Carousel,
      CarouselSlide
    }
  }
</script>

<style>
html, body{
  margin: 0;
  padding: 0;
}
</style>

<template>
  <div class="carousel">
    <slot>
    </slot>
    <button class="carousel_nav carousel_prev" @click.prevent="prev">Prev</button>
    <button class="carousel_nav carousel_next" @click.prevent="next">Next</button>
    <div class="carousel_pagination">
      <button v-for="n in slidesCount" @click.prevent="goto(n-1)" :class="{active: n-1 == index}"></button>
    </div>
  </div>
</template>

<script>
  export default {
    data() {
      return {
        index: 0,
        slides: [],
        direction: null
      }
    },
    mounted() {
      // Cada um dos elementos filhos do elemento carousel será tratado como um slide
      this.slides = this.$children;
      // Atribuir um index para cada um dos slides
      this.slides.forEach((slide, i) => {
        slide.index = i;
      });
    },
    computed: {
      slidesCount() {
        return this.slides.length;
      }
    },
    methods: {
      prev() {
        this.index--;
        this.direction = 'left';
        // Se for menor que o primeiro, ir para o último
        if (this.index < 0){
          this.index = this.slidesCount - 1;
        }
      },
      next() {
        this.index++;
        this.direction = 'right';
        // Se passar do último, voltar pro primeiro
        if (this.index >= this.slidesCount) {
          this.index = 0;
        }
      },
      goto(index){
        this.direction = index > this.index ? 'right' : 'left';
        this.index = index;
      }
    }
  }
</script>

<style lang="sass" scoped>
@import 'carousel.scss';
</style>


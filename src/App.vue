<template>
  <div>
    <carousel>
      <carousel-slide v-for="n in slides" v-bind:key="n" :index="n - 1">
        <div class="slideText">
          <p>slide{{ n }}</p>
        </div>
        <img :src="'https://picsum.photos/630/300?category=futurama/' + n" height="550" width="100%" alt="">
      </carousel-slide>
    </carousel> <br>
    <button @click="addSlide" class="">Ajouter un slide</button>
    <button @click="removeSlide">supprimer un slide</button>
  </div>
</template>

<script>
import Carousel from './components/carousel/Carousel.vue'
import CarouselSlide from './components/carousel/CarouselSlide.vue'
export default {
  data () {
    return {
      slides: 5
    }
  },
  components: {
    Carousel,
    CarouselSlide
  },

  methods: {
    addSlide () {
      this.slides++
    },
    removeSlide () {
      this.slides--
    }
  }
}
</script>

<style>
.slideText{
  position: absolute;
  left: 0;
  right: 0;
  text-align: center;
  top: 50%;
  color: #FFF;
  font-size: 50px;
}
</style>

<template>
    <Carousel :autoplay="2000" :wrap-around="true">
      <Slide v-for="(slide, index) in images" :key="index">
        <img :src="slide" alt="Slide {{ index + 1 }}" class="carousel__image" />
      </Slide>
  
      <template #addons>
        <Pagination />
      </template>
    </Carousel>
  </template>
  
  <script>
  import { defineComponent } from 'vue'
  import { Carousel, Pagination, Slide } from 'vue3-carousel'
  
  import 'vue3-carousel/dist/carousel.css'
  
  export default defineComponent({
    name: 'Autoplay',
    components: {
      Carousel,
      Slide,
      Pagination,
    },
    data() {
      return {
        images: [
        //   'src/assets/img/CBN-1.jpeg',
          'src/assets/img/CBN-1.jpeg',
          'src/assets/img/CBN-2.jpeg',
          'src/assets/img/CBN-3.jpeg',
          'src/assets/img/CBN-4.jpeg',
          // Add more image URLs as needed
        ],
      }
    },
  })
  </script>
  
  <style scoped>
  .carousel__image {
    max-width: 100%;
    height: auto;
  }
  </style>
  
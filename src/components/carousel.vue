<template>
    <Carousel :items-to-show="1">
      <!-- <slide v-for="slide in 10" :key="slide">
        {{ slide }}
      </slide> -->
      <Slide v-for="(slide, index) in images" :key="index">
        <img :src="slide" alt="Slide {{ index + 1 }}" class="carousel__image" />
      </Slide>
  
      <template #addons>
        <navigation />
        <Pagination />
      </template>
    </Carousel>
  </template>
  
  <script>
  // If you are using PurgeCSS, make sure to whitelist the carousel CSS classes
  import 'vue3-carousel/dist/carousel.css'
  import { Carousel, Slide, Pagination, Navigation } from 'vue3-carousel'
  
  export default {
    name: 'App',
    components: {
      Carousel,
      Slide,
      Pagination,
      Navigation,
    },
    data() {
      return {
        images: [
          'src/assets/img/CBN-1.jpeg',
          'src/assets/img/CBN-2.jpeg',
          'src/assets/img/CBN-3.jpeg',
          'src/assets/img/CBN-4.jpeg',
          // Add more image URLs as needed
        ],
      }
    },
  }
  </script>
    <style scoped>
    .carousel__image {
      max-width: 100%;
      height: auto;
    }
    </style>
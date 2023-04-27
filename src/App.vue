<template>
  <carousel :slides="slides"> </carousel>
</template>

<script>
import Carousel from '@/components/Carousel.vue'

export default {
  components: {
    Carousel
  },
  data() {
    return {
      slides: ['/src/assets/img/1.jpg', '/src/assets/img/2.jpg', '/src/assets/img/3.jpg']
    }
  }
}
</script>

<style scoped></style>

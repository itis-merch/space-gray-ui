<template>
    <carousel :slides="slides">

    </carousel>
</template>

<script>
import Carousel from "@/components/Carousel.vue"

export default {
    components: {
        Carousel,
    },
    data () {
        return {
            slides: [
                "/img/1.jpg",
                "/img/2.jpg",
                "/img/3.jpg",
            ]
        }
    }
}
</script>

<style scoped>

</style>
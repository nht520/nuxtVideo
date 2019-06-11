<template>
    <div class="carousel">
        <v-carousel hide-controls>
            <v-carousel-item
            v-for="(item,i) in items"
            :key="i"
            :src="item.src"
            ></v-carousel-item>
        </v-carousel>
    </div>
</template>

<script>
export default {
    props:["items"],
    data(){
        return{
            // items: [
            //     {
            //         src: 'https://cdn.vuetifyjs.com/images/carousel/squirrel.jpg'
            //     },
            //     {
            //         src: 'https://cdn.vuetifyjs.com/images/carousel/sky.jpg'
            //     },
            //     {
            //         src: 'https://cdn.vuetifyjs.com/images/carousel/bird.jpg'
            //     },
            //     {
            //         src: 'https://cdn.vuetifyjs.com/images/carousel/planet.jpg'
            //     }
            // ]
        }
    }
}
</script>
<style lang="stylus" scoped>
 .v-carousel
  height 210px !important
</style>

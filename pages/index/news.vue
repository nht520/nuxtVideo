<template>
    <div>
      <!-- 头部 -->
      <Carousel :items="slideimg"></Carousel>
      <v-container grid-list-md text-xs-center>
        <v-layout row wrap>
            <v-flex xs12 sm6 offset-sm3>
              <v-card>
                <v-img
                  src="https://cdn.vuetifyjs.com/images/cards/desert.jpg"
                  aspect-ratio="2.75"
                ></v-img>
                <v-card-title primary-title>
                    <h5>Kangaroo Valley Safari</h5>
                    <h6>https://cdn.vuetifyjs.com/images/cards/des</h6>
                </v-card-title>
                <v-card-actions>
                  <v-btn flat color="orange">Share</v-btn>
                  <v-btn flat color="orange">Explore</v-btn>
                </v-card-actions>
              </v-card>
            </v-flex>
        </v-layout>
      </v-container>
    </div>
</template>

<script>
import Carousel from '~~/components/Carousel';
export default {
  // 页面切换动画
  transition:"transleft",
  components:{
    Carousel
  },
  data(){
    return{
        slideimg: [
          {
              src: 'https://cdn.vuetifyjs.com/images/carousel/squirrel.jpg'
          },
          {
              src: 'https://cdn.vuetifyjs.com/images/carousel/sky.jpg'
          },
          {
              src: 'https://cdn.vuetifyjs.com/images/carousel/bird.jpg'
          },
          {
              src: 'https://cdn.vuetifyjs.com/images/carousel/planet.jpg'
          }
      ],
    }
  }
}
</script>

<style>

</style>

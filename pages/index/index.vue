<template>
    <div class="indexlist">
        <!-- 轮播 -->
        <Carousel :items="slideimg"></Carousel>
        <!-- 列表 -->
        <v-container grid-list-md text-xs-center>
            <v-layout row wrap>
                <v-flex xs6 v-for="item in list" :key="item.id">
                   <nuxt-link :to="'/homedetails/'+item.id" tag="li" >
                        <v-card>
                            <v-img
                            :src="item.mealImage"
                            aspect-ratio="2.75"></v-img>
                            <v-layout row wrap class="hmdetils">
                                <v-flex xs12>
                                    <h5>{{item.mealName}}</h5>
                                </v-flex>
                                <v-flex xs6>
                                <span> 数量：{{item.mealNum}}</span>
                                </v-flex>
                                <v-flex  xs6>
                                    <span> 价格：{{item.mealPrice}}</span>
                                </v-flex>                           
                            </v-layout>
                        </v-card>
                   </nuxt-link>
                </v-flex>
            </v-layout>
        </v-container>
    </div>
</template>

<script>
import Carousel from '~/components/Carousel';
import Axios from 'axios';
export default {
    // 页面切换动画
   transition:"transleft",
   // Called to know which transition to apply
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
        list:[]
       }
   }, 
   methods:{
       homeget(){
           const api = window.g.meal;
           Axios.get(api).then((res)=>{
               console.log(res)
               this.list = res.data.records;
           }).catch((err)=>{
               console.log(err)
           })
       }
   },
   mounted(){
       this.homeget();
   }
}
</script>

<style lang="stylus" scoped>
   .text-xs-center
    padding-bottom: 75px;     
   .indexlist .row
    text-align left  
   .indexlist li  
    list-style none  
   .indexlist .row .v-image 
    height 120px  
   .indexlist .v-card
    border-radius 5px
    margin-bottom 5%
   .hmdetils
    padding 3% 
   .hmdetils h5
    font-size 15px
   .hmdetils p 
    color #6d6d6d
    font-size 14px
   .hmdetils span
    font-size 14px
</style>


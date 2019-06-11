<template>
    <div>
        <!-- 头部 -->
        <Headerone :headTitle="text"></Headerone>
        <!-- 视频 -->
        <video width="100%"   poster="http://avenecdn.witpos.cn/93dccd85cff9123bbc3644ff86493305.png"   height="240" controls> 
         <source src="http://www.17sucai.com/preview/119710/2014-10-22/%E6%96%B0%E5%BB%BA%E6%96%87%E4%BB%B6%E5%A4%B9/BigBuckBunny_640x360.mp4" type="video/mp4">
        </video>
        <!-- 详情 -->
        <v-container grid-list-md text-xs-center>
            <v-layout row wrap>
                <v-layout row wrap class="details">
                    <v-flex xs12>
                        <h5>{{details.mealName}}</h5>
                    </v-flex>
                    <v-flex xs12>
                        <p>{{details.mealContent}}</p>
                    </v-flex>
                    <v-flex xs6>
                    <span> 数量：{{details.mealNum}}</span>
                    </v-flex>
                    <v-flex  xs6>
                        <span> 价格：{{details.mealPrice}}</span>
                    </v-flex>                           
                </v-layout>
            </v-layout>
        </v-container>
    </div>
</template>

<script>
import Headerone from '~~/components/Headerone';
import Axios from 'axios';
export default {
    // 页面切换动画
    transition:"transleft",
    components:{
        Headerone
    },
    data(){
        return{
            text:"详情",
            details:[],
        }
    },
    methods:{
        detsget(){
            const detsId = this.$route.params.mealdetails;
            const api =window.g.mealDts;
            const date ={
                params:{
                    id:detsId
                }
            }
            Axios.get(api,date).then((res)=>{
                console.log(res);
                this.details = res.data.data;
                // 字符串截取
                const str=res.data.data.mealWheel;
                console.log("原字符串:",str)
                this.imgurl=str.split(',')
                console.log("转成的数组:",this.imgurl)
            }).catch((err)=>{
                console.log(err)
            })
        }
    },
    mounted(){
        this.detsget()
    }
}
</script>
<style lang="stylus" scoped>
    .details
     text-align left 
</style>


<template>
    <div class="Navigation">
        <v-card
            class="hide-overflow"
        >
            <v-bottom-nav
            :active.sync="activeBtn"
            :value="showNav"
             fixed
            shift 
            >
            <nuxt-link v-for="item in list" :to="item.path" tag="li" :key="item.id">
                 <v-btn flat color="red">
                    <span>{{item.title}}</span>
                    <v-icon>{{item.icon}}</v-icon>
                </v-btn>
            </nuxt-link>
            </v-bottom-nav>
        </v-card>
    </div>
</template>
<script>
export default {
    name:"Navigation",
    data(){
        return{
            activeBtn: 0,
             showNav: true,
             list:[
                 {
                     id:0,
                     title:"首页",
                     icon:"music_note",
                     path:"/"
                 },
                {
                     id:1,
                     title:"分类",
                     icon:"book",
                     path:"/class"
                 },
                {
                     id:2,
                     title:"热门",
                     icon:"ondemand_video",
                     path:"/news"
                 },
                {
                     id:3,
                     title:"我的",
                     icon:"image",
                     path:"/about"
                 }
             ]
        }
    },
    methods:{

    },
    mounted(){

    },
}
</script>
<style lang="stylus">
    .bottom
     list-style none
    .Navigation .v-sheet
     border-radius 0px
    .Navigation li
     list-style none
</style>

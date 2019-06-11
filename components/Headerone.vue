<template>
    <div>
        <v-card
            color="lighten-4"
            flat
            tile
        >
            <v-toolbar prominent >
            <v-btn icon light @click="goreturn()">
                <v-icon color="grey darken-2">arrow_back</v-icon>
            </v-btn>
            <v-toolbar-title>{{headTitle}}</v-toolbar-title>
            <!-- <v-spacer></v-spacer> -->
            <!-- <v-btn icon light>
                <v-icon color="grey darken-2">arrow_back</v-icon>
            </v-btn>
            <v-btn icon>
                <v-icon>favorite</v-icon>
            </v-btn>
            <v-btn icon>
                <v-icon>more_vert</v-icon>
            </v-btn> -->
            </v-toolbar>
        </v-card>
    </div>
</template>

<script>
    export default {
        props:['headTitle'],
        data(){
            return{
             title:"默认"
            }
        },
        methods:{
           header(){
               if(this.headTitle === null || this.headTitle === undefined){
                 this.headTitle = this.title
               }
           },
           goreturn(){
            this.$router.go(-1)
           }     
        },
        mounted(){
            this.header()
        }
    }
</script>

<style>

</style>

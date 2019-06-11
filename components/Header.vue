<template>
    <div>
        <v-card
            color="grey lighten-4"
            flat
            tile
        >
            <v-toolbar prominent >
            <v-toolbar-side-icon></v-toolbar-side-icon>
            <v-toolbar-title>{{headTitle}}</v-toolbar-title>
            <v-spacer></v-spacer>
            <v-btn icon>
                <v-icon>search</v-icon>
            </v-btn>
            <v-btn icon>
                <v-icon>favorite</v-icon>
            </v-btn>
            <v-btn icon>
                <v-icon>more_vert</v-icon>
            </v-btn>
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
           }     
        },
        mounted(){
            this.header()
        }
    }
</script>

<style>

</style>

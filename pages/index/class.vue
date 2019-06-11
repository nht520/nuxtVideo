<template>
    <div>
        111
        <v-btn color="error" @click="nuxtDialog()">Error</v-btn>
        <Dialogs ref="dialog" :hedTitle="title" :hint="hint" :del="del"></Dialogs>
    </div>
</template>

<script>
import Dialogs from '~~/components/Dialogs'
export default {
  // 页面切换动画
  transition:"transleft",
  components:{
    Dialogs
  },
  data(){
    return{
       hint:"是否确认购买",
       title:"提示?",
    }
  },
  methods:{
    nuxtDialog(){
      this.$refs.dialog.nuxtDialog();
    },
    del(){
      alert("确认删除")
    }
  },
  mounted(){
    
  }
}
</script>

<style>

</style>

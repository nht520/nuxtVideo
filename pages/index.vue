<template>
 <div>
   <nuxt-child></nuxt-child>
   <!-- 底部 -->
   <Navigation></Navigation>
 </div>
</template>
<script>
import Navigation from '~/components/Navigation';
export default {
    // 页面切换动画
  transition:"transleft",
  // 
  asyncData() {
    return new Promise((resolve) => {
      setTimeout(function () {
        resolve({})
      })
    })
  },
  components: {
    Navigation
  },
  data() {
    return {
      
    }
  },
}
</script>

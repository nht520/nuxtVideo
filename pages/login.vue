<template>
    <div>
        登录
        <nuxt-link to="/index" >54545</nuxt-link>
    </div>
</template>

<script>
export default {
  // 加载动画
  asyncData() {
    return new Promise((resolve) => {
      setTimeout(function () {
        resolve({})
      },400)
    })
  },
}
</script>

<style>

</style>

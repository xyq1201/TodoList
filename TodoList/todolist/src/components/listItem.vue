<template>
<!-- 点击事件 -->
<li @click="handleInfo">
{{content}}
</li>

</template>

<script>
export default {
  // 接收父组件的传值
  props:['content','index'],
  methods:{
    handleInfo(){
      // alert('abc')
      // 触发父组件自定义delete事件，并传入相应下标
      this.$emit('delete',this.index)
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>

<template>
  <div>
    <div>
      <input type="text" placeholder="请输入内容" v-model="newValue"/>

      <button @click="handleSubmit">提交</button>
    </div>
     <ul>
       <!-- 父组件删除事件 -->
       <todo-item v-for="(item,index) in lists" :key="index" 
       :content="item" :index="index" @delete="handleDelete(index)"></todo-item>
     </ul>
  </div>
</template>
<script>
// 引入
import listItem from './components/listItem'
export default {
  // 映射组件
  components:{
    'todo-item':listItem
  },
  data(){
    return{
      newValue:'',
      lists:[]
    }
  },
  methods:{
    handleSubmit(){
      this.lists.push(this.newValue) 
      this.newValue = ''
    },
    handleDelete(index){
      this.lists.splice(index,1)
    }
  }
}
</script>
<style lang="scss">

</style>

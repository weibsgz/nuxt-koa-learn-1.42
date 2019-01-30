<template>
    <div class="page">
        Page is Search

        <ul>
            <li v-for="(item,index) in $store.state.city.list" :key= "index">
                {{item}} 
                <!-- 打印出a , b ,c -->
            </li>

             <li v-for="(item,index) in list" :key= "index">
                {{item}}
            </li>
        </ul>
    </div>
</template>

<script>
import axios from 'axios'
export default {
  layout:'myOwenTemplate',
  data() {
      return {
          list : []
      }
  },
//   async mounted() {
//       //传统方式
//       // 解构赋值 是 AXIOS 固定格式
//       let {status,data:{list}} = await axios.get('/city/list')      
//       if(status == 200) {
//           this.list = list
//       }
//   }

 // 内部不能使用THIS了 找不到VUE实列 用return 
  async asyncData() {
      let {status,data:{list}} = await axios.get('http://localhost:3000/city/list')      
      if(status == 200) {
         return {
             list : list
         }
      }
  }
}
</script>

<style lang="css">
</style>



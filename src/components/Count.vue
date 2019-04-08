// 访问状态对象
<template>
<div>
    <h3>{{msg}}</h3>
    <p>{{$store.state.count}}-{{count}}</p>
     <p>{{count}}</p>
    <button @click="$store.commit('add')">+</button>
     <button @click="$store.commit('reduce')">-</button>
</div>
</template>
<script>
import store from '@/vuex/store'
//第二种
import { mapState } from 'vuex'
export default {
    data(){
           return{
        msg:'Hello vuex'
    }
    },
    //第一种方法：利用计算属性
    // computed: {
    //     count(){
    //         return this.$store.state.count;
    //     }
    // },

    ////第二种
    // computed: mapState({
    //     count:state=>state.count
    //     // 等同于
    //     // count:function(state){
    //     //     return state.count;
    //     // }
    // }),

   // 第三种 利用数组
   computed:mapState(['count']),
    store
 
}
</script>

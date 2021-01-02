<template>
  <div id="app">
      <h3>App组件</h3>
      <p v-bind:title="message">{{message}}</p>
      <p v-if="seen">好好学习天天向上</p>
      <button @click="toggleSeen">添加/移除</button><hr/>
      <ul>
        <li v-for="value in data" v-bind:key="value.id">
          学号：{{value.id}}
          姓名：{{value.name}}
          年龄：{{value.age}}
          性别：{{value.sex}}
        </li>
      </ul>
      <button @click="addstu">点击添加学生</button><hr/>
      <todo-item></todo-item><hr/>
      <Child v-bind:message="message"></Child>
  </div>
</template>

<script>
 import Vue from 'vue'
 import Child from "./components/Child.vue"
 Vue.component("todo-item",{
   template:`<div>
                <h3>todo-item</h3>
            </div>
  `
 })
export default {
  components: { Child },
  name: 'App',
  data(){
    return {
      message:"我是帅哥",
      seen:true,
      comments:{
        Child
      },
       data:[
          {id:1,name:"tom",age:19,sex:"男"},
          {id:2,name:"jarry",age:21,sex:"男"},
          {id:3,name:"susan",age:19,sex:"女"},
      ]
    }
  },
  methods: {
    toggleSeen(){
      if(this.seen){
        this.seen=false;
      }else{
        this.seen=true;
      }
    },
    addstu(){
      this.data.push({id:4,name:"赵四",age:43,sex:"男"})
    }
  }
}
</script>


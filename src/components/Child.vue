<template>
    <div>
        <h3>Child组件</h3>
        <p>{{msg}}</p>
        <button @click="changemsg">点击</button>
        <p>父组件传递过来的属性{{message}}</p>
    </div>
</template>

<script>
    export default {
        name:"child",
        props:['message'],
        data(){
            return {
                msg:"哈哈"
            }
        },
        methods: {
            changemsg(){
                this.msg="元旦快乐"
            }
        }
    }
</script>

<style lang="scss" scoped>

</style>
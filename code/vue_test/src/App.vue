<template>
    <div>
        <MySchool></MySchool>
        <MyStudent></MyStudent>
    </div>
</template>

<script>
    // 引入组件,es6的模块引入
    import MySchool from './components/MySchool'
    import MyStudent from './components/MyStudent'

    export default {
        name:"App",
        components:{
            MySchool:"MySchool",
            MyStudent:"MyStudent"
        }
    }
</script>

<style>

</style>
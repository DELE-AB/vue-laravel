<template>
    <header>
        <h1>{{title}}</h1>
        <Button text="Add Task" color= "red" />
    </header>
</template>

<script>
import Button from "./Button"
export default {
    name: 'Header',
    props:{
        title:String, 
    },
    components:{
        Button,
    },

}
</script>

<style scoped> /**using scoped means that all the css if specifically meant for just this component. */
header{
    display: flex;
    justify-content: space-between;
    align-items: center;
    margin-bottom: 20px;
}
</style>
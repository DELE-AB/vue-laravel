<template>
    <header>
        <h1>{{title}}</h1>
        <Button :text="showAddTask ? 'close' : 'Add Task' " :color="showAddTask ? 'red' : 'green'" @btn-click="$emit('toggle-add-task')" />
    </header>
</template>

<script>
import Button from "./Button"
export default {
    name: 'Header',
    props:{
        title: String, 
        showAddTask: Boolean,
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
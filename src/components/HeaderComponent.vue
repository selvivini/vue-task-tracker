<template>
    <header>
        <h1>{{ title }}</h1>
        <ButtonComponent class="btn" :color="showAddTask? 'red': 'green'" 
        :text="showAddTask ? 'close': 'Add Task' "
        @toggle-add-task= "$emit('toggle-add-task')"/>
    </header>
    
</template>


<script>
import ButtonComponent from './ButtonComponent.vue';

export default {
    name: 'HeaderComponent',
    components:{
     ButtonComponent
    },
    props: {
        title: String,
        showAddTask: Boolean
    }
}
</script>

<style scoped>
header {
    display: flex;
    justify-content: space-between;
    align-items: center;
    margin-bottom: 20px;
}
</style>
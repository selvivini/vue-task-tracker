<template>
<div :key="task.id" v-for="task in tasks" >
<TaskComponent :task = "task" @delete-task= "$emit('delete-task', task.id)" @toggle-reminder= "$emit('toggle-reminder', task.id)"/>
</div>
</template>

<script >
import TaskComponent from './TaskComponent.vue'
export default{
   name: 'TasksComponent',
   props:{
       tasks: Array
   },
   components:{
       TaskComponent
   },
   emits:['delete-task', 'toggle-reminder']
}

</script>
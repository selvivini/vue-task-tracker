<template>
<div class = "container">
<HeaderComponent title = "Task-Tracker" @toggle-add-task= "toggleAddTask" :showAddTask = "showAddTask"/>
<AddTask v-show= "showAddTask" @add-task= "addTask"/>
<TasksComponent :tasks= "tasks" @delete-task= "deleteTask" @toggle-reminder = "toggleReminder"/>
</div>
 
</template>

<script>
import HeaderComponent from './components/HeaderComponent.vue'
import TasksComponent from './components/TasksComponent.vue'
import AddTask from './components/AddTask.vue'


export default {
  name: 'App',
  components: {
    HeaderComponent,
    TasksComponent,
    AddTask
},
  data(){
   return {
     tasks: [],
     showAddTask: false
   }
  },
  methods:{
   deleteTask(id){
     if(confirm('Are you sure you want to delete it?')){
      this.tasks = this.tasks.filter(t=> t.id !== id);
     }
    
   },
   toggleReminder(id){
      this.tasks = this.tasks.map(t => t.id === id? {...t, reminder: !t.reminder} : t)
   },
   addTask(newTask){
      this.tasks = [...this.tasks, newTask]
   },
   toggleAddTask(){
     this.showAddTask = !this.showAddTask
   }
  },
  created(){
    this.tasks= [
      {
        id: 1,
        text: "Doctor's Appointment",
        day: 'july 8th, 2022',
        reminder: true
        },
        {
        id: 2,
        text: "Groceries shopping",
        day: 'july 11th, 2022',
        reminder: true
        },
        {
        id: 3,
        text: "Movie time",
        day: 'july 15th, 2022',
        reminder: false
        }
    ]

    
  }
}

</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Poppins:wght@300;400&display=swap');
* {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}
body {
  font-family: 'Poppins', sans-serif;
}
.container {
  max-width: 500px;
  margin: 30px auto;
  overflow: auto;
  min-height: 300px;
  border: 1px solid steelblue;
  padding: 30px;
  border-radius: 5px;
}
.btn {
  display: inline-block;
  background: #000;
  color: #fff;
  border: none;
  padding: 10px 20px;
  margin: 5px;
  border-radius: 5px;
  cursor: pointer;
  text-decoration: none;
  font-size: 15px;
  font-family: inherit;
}
.btn:focus {
  outline: none;
}
.btn:active {
  transform: scale(0.98);
}
.btn-block {
  display: block;
  width: 100%;
}
</style>

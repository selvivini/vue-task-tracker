<template>
    <div @dblclick="$emit('toggle-reminder', task.id)" class="task" :class="[task.reminder ? 'reminder' : '', 'task']">
        <h3>{{ task.text }} <i class="fas fa-times" @click="$emit('delete-task', task.id)"></i></h3>
        <h3>{{ task.day }}</h3>
    </div>
</template>


<script>

export default {
    name: 'TaskComponent',
    props: {
        task: Object
    },
    methods: {
        onDelete(id) {
            this.$emit('delete-task', id)
        }
    }
}
</script>


<style>
.fas {
    color: red;
}

.task {
    background: #f4f4f4;
    margin: 5px;
    padding: 10px 20px;
    cursor: pointer;
}

.task.reminder {
    border-left: 5px solid green;
}

.task h3 {
    display: flex;
    align-items: center;
    justify-content: space-between;
}
</style>
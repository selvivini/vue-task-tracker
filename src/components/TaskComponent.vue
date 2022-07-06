<template>
    <div class="task">
        <h3>{{ task.text }}</h3>
        <h3>{{ task.day }}</h3>
    </div>
</template>


<script>

export default {
    name: 'TaskComponent',
    props: {
        task: Object
    }
}
</script>


<style>
.task {
    background: #f4f4f4;
    margin: 5px;
    padding: 10px 20px;
    cursor: pointer;
}
</style>
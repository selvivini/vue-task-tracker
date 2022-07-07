<template>
<button @click = "onClick()" :style="{background: color}">{{text}}</button>
</template>

<script>

export default{
    name: 'ButtonComponent',
    props:{
        color: String,
        text: String
    },
    methods:{
        onClick(){
         this.$emit('toggle-add-task')
        }
    }
}
</script>


<style>
</style>
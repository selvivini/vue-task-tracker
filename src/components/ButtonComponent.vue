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
         console.log("clicked")
        }
    }
}
</script>


<style>
</style>
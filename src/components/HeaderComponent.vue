<template>
    <header>
        <h1>{{ title }}</h1>
        <ButtonComponent class="btn" color="green" text="Add Text"/>
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
        title: String
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
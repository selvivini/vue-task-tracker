<template>
    <header>
        <h1>{{ title }}</h1>
        <ButtonComponent v-show="homePage" class="btn" :color="showAddTask ? 'red' : 'green'"
            :text="showAddTask ? 'close' : 'Add Task'" @toggle-add-task="$emit('toggle-add-task')" />
    </header>

</template>


<script>
import ButtonComponent from './ButtonComponent.vue';

export default {
    name: 'HeaderComponent',
    components: {
        ButtonComponent
    },
    props: {
        title: String,
        showAddTask: Boolean
    },
    computed: {
        homePage() {
            if (this.$route.path === '/') {
                return true
            } else {
                return false
            }
        }
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
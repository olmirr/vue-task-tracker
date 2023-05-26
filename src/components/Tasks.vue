<template>
    <div v-for="task in tasks" :key="task.id">
        <Task :task="task" @toggle-reminder="$emit('toggle-reminder', task.id)" @delete-task="$emit('delete-task', task.id)"></Task>
    </div>
</template>

<script>
    import Task from './Task.vue'
    export default {
        name: 'my-tasks',
        props: {
            tasks: Array
        },
        components: {
            Task
        },
        emits: ['delete-task', 'toggle-reminder']
    }
</script>

<style scoped>

</style>

<template>
    <div @click='$emit("toggle-reminder", task.id)' :class="[task.reminder ? 'reminder' : '', 'task']">
        <h3>{{ task.text }}
            <i class="fas fa-times" @click.stop="$emit('delete-task', task.id)"></i>
        </h3>
        <p>{{ task.date }}</p>
    </div>
</template>

<script>
    export default {
        name: 'my-task',
        props: {
            task: Object
        },
        emits: ['toggle-reminder']
    }
</script>

<style scoped>
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

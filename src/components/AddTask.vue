<template>
    <form class="add-form" @submit.prevent="onSubmit">
        <div class="form-control">
            <label for="text">Task</label>
            <input id='text' type='text' name="text" v-model='text' placeholder="Add Task"/>
        </div>
        <div class="form-control">
            <label for="date">Date & Time</label>
            <input id='date' type="text" name="date" v-model='date' placeholder="Add Date & Time"/>
        </div>
        <div class="form-control form-control-check">
            <label for="reminder">Set Reminder</label>
            <input id='reminder' type="checkbox" v-model='reminder' name="reminder">
        </div>
        <input type="submit" value="Save Task" class="btn btn-block">
    </form>
</template>

<script>
export default {
    name: 'add-task',
    data() {
        return {
            text: '',
            date: '',
            reminder: false,
        }
    },
    methods: {
        onSubmit() {
            if (!this.text.trim()) {
                alert('Please add a text')
                return;
            }
            const newTask = {
                text: this.text,
                date: this.date,
                reminder: this.reminder
            }
            this.$emit('add-task', newTask);

            this.text = '';
            this.date = '',
            this.reminder = false;
        }
    }
}

</script>

<style scoped>
.add-form {
    margin-bottom: 40px;
}
.form-control {
    margin: 20px 0;
}
.form-control label {
  display: block;
}

.form-control input {
  width: 100%;
  height: 40px;
  margin: 5px;
  padding: 3px 7px;
  font-size: 17px;
}

.form-control-check {
  display: flex;
  align-items: center;
  justify-content: space-between;
}

.form-control-check label {
  flex: 1;
}

.form-control-check input {
  flex: 2;
  height: 20px;
}

</style>

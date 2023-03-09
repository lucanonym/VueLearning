<template>
    <form @submit="onSubmit" class="addform">
        <div class="form-control">
            <label>
                Add Task
            </label>
            <input typ="text" v-model="text" name="text" placeholder="Add Task"/>
        </div>
        <div class="form-control">
            <label>Day & Time</label>
            <input type="text" v-model="day" name="day" placeholder="Add Day and Time"/>
        </div>
        <div class="form-control form-control-check">
            <label>Set Reminder</label>
            <input type="checkbox" v-model="reminder" name="reminder"/>
        </div>
        <input type="submit" value="Save Task" class="btn btn-block"/>
    </form>
</template>

<script>
export default {
   name: 'AddTask',
   data() {
    return {
        text: '',
        day: '',
        reminder: false,
    }
   },
   methods: {
    onSubmit(e) {
        e.preventDefault();
        if (!this.text) {
            alert('Please add a Task!');
            return;
        }
        const newTask = {
            id: Math.floor(Math.random() * 1000),
            text: this.text,
            day: this.day,
            reminder: this.reminder,
        }
        this.text = '';
        this.day = '';
        this.reminder = false;
        this.$emit('add-Task', newTask);

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

.form-control input {
    display: block;
}

.form-control input {
    width: 100%;
    height: 40px;
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
.addform {
    margin-bottom: 20px;
}





</style>
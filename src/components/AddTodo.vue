<template>
    <div class="d-flex justify-content-center">
        <form class="form-inline" @submit="addTodo">
            <div class="form-group my-2">
                <input type="text" class="form-control" v-model="title" name="title" id="">
            </div>
            <div class="form-group mx-sm-3 my-2">
                <button class="btn btn-primary" type="submit">Add</button>
            </div>
        </form>    
    </div>
</template>

<script>
import { v4 as uuidv4} from 'uuid';
export default {
    name: 'AddTodo',
    data() {
        return {
            title:'',
        }
    },
    methods: {
        addTodo(e) {
            e.preventDefault();

            const newTodoObj = {
                id: uuidv4 (),
                title: this.title,
                completed: false,
            }

            this.$emit('add-todo', newTodoObj);
            this.title = '';
        }
    }
}
</script>
<template>
    <div>
        <h2>My Todolist</h2>
        <ul>
            <li v-bind:key="todo.id" v-for="todo in todos">
                <Todo v-bind:todo="todo" v-on:delete-todo="$emit('delete-todo', todo.id)" />
            </li>
        </ul>
        
        <Todo />
    </div>
</template>

<script>
import Todo from './Todo';
export default {
    name: 'Todos',
    props: [ 'todos' ],
    components: { Todo },
 
}
</script>
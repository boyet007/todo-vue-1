<template>
    <div v-if="todo" v-bind:class="{ 'completed': todo.completed }">
        <span v-on:click="markComplete" v-if="todo">{{ todo.title }}</span>
        <a href="#" class="mx-4" @click="$emit('delete-todo', todo.id)">Delete</a>
    </div>
</template>

<script>
export default {
    name: 'Todo',
    props: ['todo'],
    methods: {
        markComplete() {
            this.todo.completed =! this.todo.completed
        }
    },
}
</script>

<style scoped>
   .completed { text-decoration: line-through; }     
</style>
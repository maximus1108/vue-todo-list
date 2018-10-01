<template>
    <div>
    <ul v-for="(todo, i) in items" :key="i">
        <li 
            :style="todo.done ? { textDecoration: 'line-through' } : ''"
            v-on:click="clickTodo(i)"
        >
            {{ todo.text }}
        </li>
    </ul>
    </div>
</template>

<script>
export default {
    props: {
        items: Array
    },
    methods: {
        clickTodo(i){
            this.$emit('update-todo', i);
        }
    }
}
</script>

<style scoped>
    ul {
        list-style: none;
        padding: 0;
    }
</style>

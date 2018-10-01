<template>
    <form v-on:submit.prevent="addTodo($event)">
        <textarea name="todo"></textarea>
        <button>Add to do</button>
    </form>
</template>

<script>
export default {
    methods: {
        addTodo(e){
            const todo = new FormData(e.target).get('todo')
            if(todo){
                this.$emit('add-todo', todo);
            }
        }
    }
}
</script>

<style scoped>
    textarea {
        width: 250px;
        height: 35px;
        display: inline-block;
        vertical-align: middle;
        resize: none;
        font-family: 'Avenir', Helvetica, Arial, sans-serif;
        font-size: 12px;
    }

    button {
        margin-left: 15px;
        display: inline-block;
        vertical-align: middle;
        font-family: 'Avenir', Helvetica, Arial, sans-serif;
        font-size: 12px;
        height: 25px;
    }

</style>



<template src ="./Todos.html">
</template>

<style scoped src="./Todos.css"></style>

<script>
export default {
    props: ['todosList'],
    methods: {
        checked(todo) {
            todo.completed = !todo.completed;
            console.log(todo);
        },
        addItem(item) {
            console.log(item, this.todosList);
            const obj = {};
             obj['id'] = this.todosList.length + 1;
             obj['title'] = item;
             obj['completed'] = false;
             obj['userId'] = this.todosList.length + 1;

             this.$emit('addItem', obj);
        }
    }
}
</script>
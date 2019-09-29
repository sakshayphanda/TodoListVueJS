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
        }
    }
}
</script>
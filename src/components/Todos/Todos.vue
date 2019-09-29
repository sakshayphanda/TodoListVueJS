<template src ="./Todos.html">
</template>

<style scoped src="./Todos.css"></style>

<script>
export default {
    props: ['todosList'],
    methods: {
        checked(todo) {
            todo.isCompleted = !todo.isCompleted;

            console.log(todo);
        }
    }
}
</script>
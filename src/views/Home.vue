<template>
  <div class="home">
    <Todos v-bind:todosList="todosList"/>
  </div>
</template>

<script>
import Todos from '../components/Todos/Todos.vue'
// @ is an alias to /src


export default {
  name: 'home',
  components: {
    Todos
  },
  data() {
    return {
      todosList: [
        {
          name: 'Sakshay',
          id: 1,
          isCompleted: false
        },
        {
          id: 2,
          name: 'Lakshay',
          isCompleted: true
        },
        {
          id: 3,
          name: 'Himanshu',
          isCompleted: true
        }
      ]
    }
  }
}
</script>

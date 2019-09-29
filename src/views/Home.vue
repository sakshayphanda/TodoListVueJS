<template>
  <div class="home">
    <Todos @delete-item="deleteItem($event)" v-bind:todosList="todosList"/>
  </div>
</template>

<script>
import Todos from '../components/Todos/Todos.vue';
import axios from 'axios';
// @ is an alias to /src


export default {
  name: 'home',
  components: {
    Todos
  },
  data() {
    return {
      todosList: []
    }
  },
  methods: {
    deleteItem(id) {
      this.todosList = this.todosList.filter(
        item => item.id !== id
      );
    }
  },
  created() {
    axios.get('https://jsonplaceholder.typicode.com/todos').then(
      response => {
        console.log(response);
        this.todosList = response.data
      }
    );
  }
}
</script>

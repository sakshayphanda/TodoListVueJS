<template>
  <div class="home">
    <Todos @addItem = "addItem($event)" @delete-item="deleteItem($event)" v-bind:todosList="todosList"/>
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
    }, 
    addItem(item) {
      this.todosList = [...this.todosList, item]
    }
  },
  created() {
    axios.get('https://jsonplaceholder.typicode.com/todos?_limit=5').then(
      response => {
        console.log(response);
        this.todosList = response.data
      }
    );
  }
}
</script>

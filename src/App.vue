<template>
  <div id="app">
    <h1>To-Do List</h1>
    <ToDoForm></ToDoForm>
    <ul>
      <li v-for="item in ToDoItems" :key="item.id">
        <ToDoItem :label="item.label" v-bind:done="item.done" :id="item.id"></ToDoItem>
      </li>
    </ul>
    </div>
</template>

<script>
import ToDoItem from './components/ToDoItem.vue';
import uniqueId from 'lodash.uniqueid';
import ToDoForm from './components/ToDoForm.vue';

export default {
  name: 'App',
  components: {
    ToDoItem, 
    ToDoForm
  },
  
  data() {
    return {
      ToDoItems: [
        { id: uniqueId('todo-'), label: 'aasdasdasdasd', done: true },
        { id: uniqueId('todo-'), label: 'baaaaaaaa', done: false},
        { id: uniqueId('todo-'), label: 'ccccccccc', done: true},
        { id: uniqueId('todo-'), label: 'ddddddddddd', done: true}
      ]
    };
  }
  
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>

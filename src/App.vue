<template>
  <div>
    <AddTodo />
    <FilterTodos />
    <Todos />
  </div>
</template>
<script>
import Sidebar from './components/Sidebar.vue'
import Todos from './components/Todos.vue'
import AddTodo from './components/AddTodo.vue'
import FilterTodos from './components/FilterTodos.vue'



export default {
  name: "app",
  components: {
    Sidebar,
    Todos,
    AddTodo,
    FilterTodos
},
  methods: {
    search(val) { 
    }
  }
};
</script>
<style></style>

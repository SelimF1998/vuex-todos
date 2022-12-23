<template>
  <div>
    <h1 class="text-red-500 font-bold text-3xl mt-5 text-center">Todos</h1>
    <div class="flex gap-2 items-center justify-center">
      <h1 class="text-blue-500 font-bold text-lg mt-5 text-center">Double click to mark as complete</h1>
      <div class="completed-box flex gap-2">
        <div class="box-border h-5 w-5 p-4 bg-green-500 mt-5"></div>
        <h1 class="mt-6">Incomplete</h1>
      </div>
      <div class="incompleted-box flex gap-2">
        <div class="box-border h-5 w-5 p-4 bg-gray-500 mt-5"></div>
        <h1 class="mt-6">Complete</h1>
      </div> 
    </div>
    <div class="todos flex items-center justify-center flex-wrap gap-5 mt-5">
      <div
        @dblclick="onDblClick(todo)"
        v-for="todo in allTodos"
        :key="todo.id"
        v-bind:class="{
          'card w-96 bg-green-500 shadow-xl justify-between cursor-pointer': !todo.completed,
          'card w-96 bg-gray-500 shadow-xl justify-between cursor-pointer': todo.completed, 
        }"
      >
        <i @click="onDelete(todo.id)" class="fas fa-times flex items-end justify-end mt-2 mr-2 text-2xl text-gray-100 cursor-pointer" ></i>    
        <div class="card-body">
          <h2 class="card-title text-gray-900">{{ todo.title }}</h2>
          <p>{{ todo.description }}</p>
        </div>
      </div>
    </div>
  </div>
</template>
<script>
import {mapGetters, mapActions} from "vuex";

export default {
  name: "Todos",
  methods: {
    ...mapActions(["fetchTodos", "deleteTodo", "updateTodo"]),
    onDelete(id) {
      this.deleteTodo(id)
    },
    onDblClick(todo) {
      const updTodo = {
        id: todo.id,
        title: todo.title,
        completed: !todo.completed
      }

      this.updateTodo(updTodo)
    }
  },
  computed: mapGetters(["allTodos"]),
  created() {
    this.fetchTodos() 
  }
};
</script>
<style></style>

<template>
  <div>
    <h1 class="text-red-500 font-bold text-3xl mt-5 text-center">Todos</h1>
    <div class="todos flex items-center justify-center flex-wrap gap-5 mt-5">
      <div
        v-for="todo in allTodos"
        :key="todo.id"
        class="card w-96 bg-base-100 shadow-xl"
      >
        <div class="card-body">
          <h2 class="card-title">{{ todo.title }}</h2>
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
    ...mapActions(["fetchTodos"])
  },
  computed: mapGetters(["allTodos"]),
  created() {
    this.fetchTodos()
  }
};
</script>
<style></style>

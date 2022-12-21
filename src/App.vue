<template>
  <div class="grid items-center justify-center">
    <Todos />
  </div>
</template>
<script>
import Sidebar from './components/Sidebar.vue'
import Todos from './components/Todos.vue'

export default {
  name: "app",
  components: {
    Sidebar,
    Todos
  },
  methods: {
    search(val) { 
    }
  }
};
</script>
<style></style>

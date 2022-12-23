<template>
  <div class="grid gap-5 items-center justify-center">
    <h3 class="text-green-500 font-bold text-3xl mt-5 text-center">Add Todo</h3>
    <div class="add">
      <form @submit="onSubmit" class="flex gap-2">
        <input
          v-model="title"
          type="text"
          placeholder="Add Todo..."
          class="input w-full max-w-xs max-w-max"
        />
        <button type="submit" class="btn btn-outline btn-primary">
          Submit
        </button>
      </form>
    </div>
  </div>
</template>
<script>
import { mapActions } from "vuex";

export default {
  name: "AddTodo",
  data() {
    return {
      title: "",
    };
  },
  methods: {
    ...mapActions(["addTodo"]),
    onSubmit(e) {
      e.preventDefault();
      this.addTodo(this.title);
    },
  },
};
</script>
<style></style>

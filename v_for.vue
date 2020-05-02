<template>
  <div>
    <ul>
      <li :key="todo.id" v-for="todo in todos">
        <label>
          <input type="checkbox" v-model="todo.isDone" :checked="todo.isDone" />
          <del v-if="todo.isDone">{{ todo.text }}</del>
          <span v-else>{{ todo.text }}</span>
        </label>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  data() {
    return {
      todos: [
        { id: 1, text: "タスク1", isDone: false },
        { id: 2, text: "タスク2", isDone: false },
        { id: 3, text: "タスク3", isDone: false },
        { id: 4, text: "タスク4", isDone: true },
        { id: 5, text: "タスク5", isDone: false }
      ]
    };
  },
  methods: {
    toggle(todo) {
      todo.done = !todo.done;
    }
  }
};
</script>

<style>
</style>
<template>
  <div id="app">
    <input v-model="text">

    <button @click="addTodo()">決定</button>

    <ul>
      <li v-for="(todo, index) in todos" :key="index">
        {{ todo }}<button @click="removeTodo(index)">完了</button>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: "App",

  // モノ
  data() {
    return {
      text: "",
      todos: []
    };
  },

  // 処理
  methods: {
    addTodo() {
      // 追加
      this.todos.push(this.text);
      this.text = "";
    },
    removeTodo(removeIndex) {
      // 削除
      this.todos.splice(removeIndex, 1);
    }
  }
};
</script>

<style>
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
  margin-top: 60px;
}
</style>

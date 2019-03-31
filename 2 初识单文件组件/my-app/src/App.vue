<template>
  <div id="app">
    Hello World {{ msg }}
    <div>
      <input type="text" v-model="info">
    </div>
    <button @click="handleClick">添加</button>
    <ul>
      <todo-item v-for="item in list" :key="item">
        <template v-slot:item="itemProps">
          <span :style="{fontSize: '20px', color: itemProps.checked?'red':'blue'}">{{ item }}</span>
        </template>
      </todo-item>
    </ul>
  </div>
</template>

<script>
import TodoItem from "./components/TodoItem.vue";

export default {
  name: "app",
  data() {
    return {
      msg: "I'm Draper",
      info: "",
      list: []
    };
  },
  methods: {
    handleClick() {
      this.list.push(this.info);
      this.info = "";
    }
  },
  components: {
    TodoItem
  }
};
</script>

<style>
</style>

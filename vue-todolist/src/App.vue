<script>
export default {

//Component name:
  name: "App",

//Data option:
  data() {
    return {
      todos: [],
      newTodo: ""
    };
  },
  //Methods option:
  methods: {
    addTodo() {
      if (this.newTodo) {
        this.todos.push({ text: this.newTodo, done: false });
        this.newTodo = "";
      }
    },
  },
}; //End script

</script>

<template>
  <div class="container my-20 max-w-lg">
    <!-- Add todo list -->
    <div class="flex">
      <input class="rounded" type="text" v-model="newTodo" placeholder="To Do List" @keyup.enter="addTodo" />
      <button class="ml-4 rounded bg-black px-6 text-white" @click="addTodo">Add</button>
    </div>

    <!-- List of todos -->
    <ul class="mt-8">
      <li class="mt-4 flex items-center rounded bg-slate-200 p-4" v-for="(todo, index) in todos" :key="index">
        <input class="rounded border-0 " type="checkbox" v-model="todo.done"/>
        <div class="ml-3 mr-8" :class="todo.done?'fatto':''">{{ todo.text }}</div>
        <button class="ml-auto text-red-400" @click="todos.splice(index, 1)">Cancel</button>
      </li>
    </ul>
  </div>
</template>

<style>
.fatto {
  text-decoration: line-through;
}
</style>

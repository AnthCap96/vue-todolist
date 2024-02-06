<script>
export default {

//Component name:
  name: "App",

//Data option:
  data() {
    return {
      todos: [],
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
  <div>
    
  </div>
  

</template>

<style>
</style>
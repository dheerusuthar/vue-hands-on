<template>
  <div>
    <div class="todo-item" v-bind:class="{'is-complete':todo.completed}">
      <p>
        <input type="checkbox" v-on:change="markComplete">
        {{todo.title}}
        <button class="del" @click="$emit('del-todo', todo.id)">x</button>
      </p>
    </div>
  </div>
</template>

<script>
export default {
  name: "ToDoItem",
  props: ["todo"],
  methods: {
    markComplete() {
      console.log("marked compslete");
      this.todo.completed = !this.todo.completed;
    }
  }
};
</script>


<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.todo-item {
  background: #f4f4f4;
  padding: 10px;
  border-bottom: 1px #ccc dotted;
}
.is-complete {
  text-decoration: line-through;
}
.del {
  background: #ff0000;
  color: #fff;
  border: none;
  padding: 5px 9px;
  border-radius: 50%;
  cursor: pointer;
  float: right;
}
</style>

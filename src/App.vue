<template>
  <div class="todo">
    <div class="form-group">
      <h1>
        <span class="vue">Vue</span> To-Do
        <small>List</small>
      </h1>
      <form role="form">
        <input
          v-model="title"
          type="text"
          class="form-control"
          placeholder="해야 할 일" />
      </form>
      <button
        type="button"
        class="btn btn btn-primary"
        @click="addToDo(title)">
        Add
      </button>
    </div>
    <div class="todo-list">
      <ToDoList
        :todos="todos"
        @del-todo="delToDo" />
    </div>
  </div>
</template>

<script>
import ToDoList from '~/components/ToDoList.vue'
export default {
  components: {
    ToDoList
  },
  data() {
    return {
      title: '',
      todos: [
        {
          title: '운동하기'
        },
        {
          title: 'JAVA'
        },
        {
          title: 'javascript'
        }
      ]
    }
  },
  methods: {
    addToDo(title) {
      if(title) {
        this.todos.push({title})
      }
    }
  }
}
</script>

<style scoped lang="scss">
.todoApp {
  margin: auto;
  width: 500px;
}
form {
    display: inline-block;
}
.form-group {
    text-align: center;
    margin-top: 10em;
    padding-bottom: 25px;
}
.todo-list {
    width: 250px;
    text-align: left;
    margin-left: 130px;
}
a.close {
    float: right;
}
.vue {
    color: #009900;
}
</style>

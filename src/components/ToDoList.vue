<template>
  <div>
    <ul
      v-for="(todo,i) in todos"
      :key="todo.id"
      class="list-unstyled">
      <li>
        {{ i+1 }}. {{ todo.title }} <span
          class="close"
          aria-hidden="true">&times;</span>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  props: {
    todos: {
      type: Array,
      default: undefined
    },
    methods: {
      delToDo (todo) {
        this.$emit('del-todo', todo)
      }
    }
  }
}
</script>

<template>
  <div>
    <ul>
      <TodoItem
        v-for="(todo, i) of todos"
        v-bind:key="todo.id"
        v-bind:todo="todo"
        v-bind:index="i"
        v-on:remove-todo="removeTodo"
      />
    </ul>
  </div>
</template>

<script>
    import TodoItem from './TodoItem'

    export default {
        name: 'TodoList',
        props: ['todos'],
        components: {
            TodoItem
        },
        methods: {
            removeTodo (id) {
                this.$emit('remove-todo', id)
            }
        }
    }
</script>

<style scoped lang="scss">
  ul {
    list-style: none;
    margin: 0;
    padding: 0;
  }
</style>

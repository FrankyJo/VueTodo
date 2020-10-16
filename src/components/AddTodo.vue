<template>
  <form @submit.prevent="onSubmit">
    <input type="text" v-model="title">
    <button type="submit">Create</button>
  </form>
</template>

<script>
    export default {
        name: 'addTodo',
        data () {
            return {
                title: ''
            }
        },
        methods: {
            onSubmit () {
                if (this.title.trim()) {
                    const newTodo = {
                        id: Date.now(),
                        title: this.title,
                        completed: false
                    }
                    this.$emit('add-todo', newTodo)
                }
            }
        }
    }
</script>

<style scoped>
  form {
    display: flex;
    margin-bottom: 20px;
    justify-content: center;
  }

  input {
    width: 400px;
  }
</style>

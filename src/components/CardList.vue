<template>
  <div class="card-container">
      <card v-for="todo in todos" v-bind:key="todo" :description="todo.first_name"></card>
  </div>
</template>

<script>
import axios from "axios"

import Card from "@/components/Card"

export default {
  name: "CardList",
  components: { Card },
  data () {
    return {
      todos: [],
      errors: []
    }
  },
  async created () {
    try {
      const response = await axios.get("https://reqres.in/api/users?page=2")
      this.todos = response.data.data
    } catch (e) {
      this.errors.push(e)
    }
  }
}
</script>


<style lang="scss" scoped>
.card-container {
    display: flex;
}
</style>



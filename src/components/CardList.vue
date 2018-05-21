<template>
  <div class="card-container">
      <card v-for="todo in todos" v-bind:key="todo" :description="todo.first_name" :detail="todo.last_name"></card>
  </div>
</template>

<script>
import axios from "axios"

import Card from "@/components/Card"

export default {
  name: "TodoList",
  components: { card: Card },
  data () {
    return {
      todos: [],
      errors: []
    }
  },
  async created () {
    try {
      this.todos = [{first_name: "loading..."}]
      const response = await axios.get("https://reqres.in/api/users?page=2")
      this.todos = response.data.data
    } catch (e) {
      this.errors.push(e)
    }
  }
}
</script>

<style lang="scss" scoped>
@import "../../node_modules/bootstrap/scss/_functions";
@import "../../node_modules/bootstrap/scss/_variables";
@import "../../node_modules/bootstrap/scss/mixins/_breakpoints";

.card-container {
  display: flex;

  @include media-breakpoint-down(sm) {
    flex-direction: column;
  }
}
</style>

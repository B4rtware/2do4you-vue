<template>
  <div class="card">
    <div class="card-header">{{ description }}</div>
    <div class="card-body">Hier könnte viel text stehen</div>
  </div>
</template>

<script>
export default {
  name: "TodoCard",
  props: {
    description: {
      type: String,
      required: true
    }
  }
}
</script>

<style lang="scss" scoped>
.card {
  margin: 2px;
}
</style>

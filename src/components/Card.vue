<template>
  <div class="card">
    <div class="card-header">{{ description }}</div>
    <div class="card-body">{{ detail }}</div>
    <div class="card-footer">
      <div class="row">
        <div class="col">
          <div class="btn btn-danger">Delete</div>
        </div>
        <div class="col">
          <div class="btn btn-primary">Edit</div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "TodoCard",
  props: {
    description: {
      type: String,
      required: true
    },
    detail: {
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

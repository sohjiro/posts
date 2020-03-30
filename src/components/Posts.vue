<template>
  <div>
    <div class="media">
      <img src="https://via.placeholder.com/64" class="align-self-start mr-3" alt="...">
      <div class="media-body">
        <h5 class="mt-0">{{ post.title }}</h5>
        {{ post.body }}
      </div>
    </div>
  </div>
</template>

<script>

export default {
  props: {
    post: {
      id: Number,
      title: String,
      body: String,
      userId: Number
    }
  }
}
</script>

<style scoped>
</style>


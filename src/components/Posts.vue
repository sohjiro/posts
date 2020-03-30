<template>
  <div>
    <div class="card w-75">
      <div class="card-body">
        <div class="card-title">
          <img :src=image class="rounded-circle" width="50px" alt="...">
          Usuario
        </div>

        <p class="card-text"> {{ post.body }} </p>
        <div class="row">
          <div class="col-md-4">
            <div class="card-text">
              <small class="text-muted">3 years ago</small>
            </div>
          </div>
          <div class="col-md-8 text-right">
            <button type="button" class="btn btn-light" @click="counter += 1"> {{ counter }} ♡</button>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>

export default {
  data: function() {
    return {
      counter: 0
    }
  },
  props: {
    post: {
      id: Number,
      title: String,
      body: String,
      userId: Number
    }
  },
  computed: {
    image: function() {
      let fileName = this.post.id % 2 == 0 ? "dog.png" : "cat.jpg"

      return require(`../assets/${fileName}`)
    }
  }
}
</script>

<style scoped>
</style>


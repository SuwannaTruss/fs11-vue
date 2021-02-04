<template>
  <div class="container">
    <h2>ADD NEW PROJECT</h2>
    <!-- use v-model to get input, assign to props -->
    <div class="mb-4">
      <label for="title">Project Title</label>
      <input v-model="title" id="title" class="form-control" />
    </div>

    <div class="mb-4">
      <label for="image">Image URL</label>
      <input v-model="image" id="image" class="form-control" />
    </div>

    <div class="mb-4">
      <label for="description">Project Description</label>
      <textarea
        v-model="description"
        id="description"
        class="form-control"
      ></textarea>
    </div>

    <!-- use @click, is same with 'addEventListener ("click")' -->
    <button @click="handleSubmit" class="btn btn-primary">SUBMIT</button>
  </div>
</template>

<script>
export default {
  name: "AdminView",
  data() {
    return {
      title: "",
      image: "",
      description: ""
    };
  },
  methods: {
    handleSubmit() {
      this.$emit("createProject", {
        title: this.title,
        image: this.image,
        description: this.description
      });
    }
  }
};
</script>

<style>
/* * {
  align-items: center;
  text-align: center;
} */
</style>

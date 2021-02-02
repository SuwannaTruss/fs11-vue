<template>
  <div>
    <h2>ADD NEW PROJECT</h2>
    <!-- use v-model to get input, assign to props -->
    <div>
      Project Title
      <input v-model="title" />
    </div>
    <div>
      Image URL
      <input v-model="image" />
    </div>
    <div>
      Project Description
      <input v-model="description" />
    </div>

    <!-- use @click, is same with 'addEventListener ("click")' -->
    <button @click="handleSubmit">SUBMIT</button>
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
* {
  align-items: center;
  text-align: center;
}
</style>

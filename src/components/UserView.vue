<template>
  <div class="container">
    <div class="d-flex flex-row mb-4">
      <div class="row col-md-6">
        <img :src="projects[selectedID].image" class="img-fluid rounded" />
      </div>
      <div class="p-4">
        <h3>{{ projects[selectedID].title }}</h3>
        <p>{{ projects[selectedID].description }}</p>
      </div>
    </div>

    <div class="row">
      <div v-for="(project, index) in projects" :key="index" class="col-3 mb-4">
        <img
          :src="project.image"
          @click="addDisplay(index)"
          class="img-fluid rounded shadow"
        />
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "UserView",
  data() {
    return {
      isSelected: false,
      selectedID: 0
      // selectedProject = project[0]
    };
  },
  props: ["projects"],
  methods: {
    addDisplay(index) {
      this.isSelected = true;
      this.selectedID = index;
      // this.selectedProject = project;
    }
  }
};
</script>

<style></style>

/* image links:
https://blogs.winona.edu/admissions/wp-content/uploads/2014/11/codingcorgi.jpg
https://i.imgur.com/wkSPiCO.jpeg https://pbs.twimg.com/media/D0HWeYcXgAAjaER.jpg
*/

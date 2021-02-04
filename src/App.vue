<template>
  <div class="container">
    <div class="nav-bar">
      <button
        @click="isAdmin = true"
        class="btn"
        :class="{ 'text-danger': isAdmin }"
      >
        ADMIN
      </button>
      <button
        @click="isAdmin = false"
        class="btn"
        :class="{ 'text-danger': !isAdmin }"
      >
        USER
      </button>
    </div>

    <h1>MY PORTFOLIO</h1>
    <!-- To use Component (3/3: 3. Use component as html tag  -->
    <admin-view v-if="isAdmin" @createProject="addProject" />
    <user-view v-else :projects="allProjects" />
  </div>
</template>

<script>
//To use Component (1/3: Import component)
import AdminView from "./components/AdminView";
import UserView from "./components/UserView";

export default {
  name: "app",
  // To use Component (2/3: Declare component)
  components: {
    userView: UserView,
    adminView: AdminView
  },
  data() {
    return {
      isAdmin: true,
      allProjects: [
        {
          title: "image 1",
          image:
            "https://www.dignited.com/wp-content/uploads/2014/05/I-heard-hes-good-at-coding-l.jpg",
          description: "Coding Dog"
        },
        {
          title: "image 2",
          image:
            "https://ctbreeder.com/wp-content/uploads/2017/05/where-to-buy-a-puppy.jpg",
          description: "Researcher Dog"
        },
        {
          title: "image 3",
          image:
            "https://image.freepik.com/free-photo/cute-jack-russell-dog-working-laptop-home-elegant-dog-wearing-bow-tie-stay-home-technology-indoors-concept_139317-5106.jpg",
          description: "coder on a Pitch day"
        },
        {
          title: "image 4",
          image:
            "https://image.freepik.com/free-photo/cute-jack-russell-dog-working-laptop-home-feeling-tired-sleepy-stay-home-technology-indoors-concept_139317-5120.jpg",
          description: "coding all night"
        }
      ]
    };
  },
  methods: {
    addProject(project) {
      this.allProjects.push(project);
    }
  }
};
</script>

<style>
.nav-bar {
  height: 60px;
  margin-top: 10px;
  margin-bottom: 10px;
  text-align: end;
}
</style>

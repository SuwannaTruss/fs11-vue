<template>
  <div>
    <h1>MY PORTFOLIO</h1>
    <button @click="isAdmin = true" :class="{ 'text-danger': isAdmin }">
      ADMIN
    </button>
    <button @click="isAdmin = false" :class="{ 'text-danger': !isAdmin }">
      USER
    </button>
    <!-- To use Component (3/3: 3. Use component as html tag  -->
    <admin-view v-if="isAdmin" @createProject="addProject" />
    <user-view v-else />
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
      allProjects: []
    };
  },
  methods: {
    addProject(project) {
      this.allProjects.push(project);
    }
  }
};
</script>

<style></style>

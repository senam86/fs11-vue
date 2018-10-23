<template>
  <div>
    <button v-on:click="isAdmin = true">ADMIN</button>
    <button v-on:click="isAdmin = false">USER</button>
    <admin-view v-if="isAdmin" @addProject="addProject"/>
    <!-- <user-view projects="projects" /> -->
  </div>
</template>


<script>
import AdminView from "./AdminView";
import UserView from "./UserView";

export default {
  name: "Main",
  components: {
    userView: UserView,
    adminView: AdminView
  },
  data: () => ({
    isAdmin: true,
    projects: []
  }),
  methods: {
    addProject: function(project) {
      this.projects.push(project);
    }
  }
};
</script>

<style>
</style>

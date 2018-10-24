<template>
  <div>
    <button @click="isAdmin = true">ADMIN</button>
    <button @click="isAdmin = false">USER</button>
    <admin-view v-if="isAdmin" @addProject="addProject"/>
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

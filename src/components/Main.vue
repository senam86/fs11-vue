<template>
  <div>
    <h1>Hello World</h1>
    <button @click="isAdmin = true">ADMIN</button>
    <button @click="isAdmin = false">USER</button>
    <admin-view v-if="isAdmin" @createProject="addProject"/>
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
    allProjects: []
  }),
  methods: {
    addProject: function(project) {
      this.allProjects.push(project);
    }
  }
};
</script>

<style>
h1 {
  color: red;
}
</style>

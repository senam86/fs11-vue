<template>
  <div>
    <h1>Hello World</h1>
    <button @click="isAdmin = true" :class="{ red: isAdmin }">ADMIN</button>
    <button @click="isAdmin = false" :class="{ red: !isAdmin }">USER</button>
    <admin-view v-if="isAdmin" @createProject="addProject" />
    <user-view v-else />
  </div>
</template>

<script>
import AdminView from "./components/AdminView";
import UserView from "./components/UserView";

export default {
  name: "app",
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

<style>
.red {
  color: red;
  background-color: seagreen;
}
</style>

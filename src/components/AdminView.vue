<template>
  <div>
    Title
    <input v-model="title">
    <button @click="handleSubmit">SUBMIT</button>
  </div>
</template>


<script>
export default {
  name: "AdminView",
  data: () => ({
    title: "",
    image: "",
    description: ""
  }),
  methods: {
    handleSubmit() {
      this.$emit("addProject", {
        title: this.title,
        image: this.image,
        description: this.description
      });
    }
  }
};
</script>

<style>
</style>

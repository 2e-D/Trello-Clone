<script setup>
import { ref } from "vue";
import { RouterLink, RouterView } from "vue-router";
import PageHeader from "./components/PageHeader.vue";
import ToDoList from "./components/ToDoList.vue";
import Footer from "./components/PageFooter.vue";
</script>

<template>
  <PageHeader></PageHeader>
  <div class="container">
    <div class="to-do-container">
      <ToDoList></ToDoList>
    </div>
  </div>

  <Footer></Footer>
</template>

<style scoped>
.to-do-container {
  margin-top: 90px;
  margin-left: 20px;
  display: flex;
  flex-direction: column;
  overflow-y: scroll;
}
</style>

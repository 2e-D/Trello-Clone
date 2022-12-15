<script setup>
import { reactive } from "vue";
import { RouterLink, RouterView } from "vue-router";
import PageHeader from "./components/PageHeader.vue";
import ToDoList from "./components/ToDoList.vue";
import Footer from "./components/PageFooter.vue";
import CreateListButton from "./components/CreateListButton.vue";

const lists = reactive([
  {
    id: 1,
    title: "To do",
    cards: [],
  },
]);

const addList = (title) => {
  lists.push({
    id: 2,
    title: title,
    cards: [],
  });
};
</script>

<template>
  <PageHeader></PageHeader>
  <div class="container">
    <div class="to-do-container">
      <ToDoList v-for="list in lists" :list="list" :key="list.id"></ToDoList>
    </div>
    <div class="ButtonDiv">
      <CreateListButton @add-list="addList"></CreateListButton>
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
  flex-direction: row;
  gap: 40px;
}

.newCardButton {
  display: flex;
  justify-content: center;
  align-items: center;
  text-align: center;
  border: solid 2px red;
}
</style>

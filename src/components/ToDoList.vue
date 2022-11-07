<script setup>
import { ref } from "vue";
import ToDoListItem from "./ToDoListItem.vue";
const listItems = ref([]);
const todo = ref("");

const AddToList = () => {
  listItems.value.push({
    task: todo.value,
    completed: false,
  });
  todo.value = "";
};

const remove = (key) => {
  this.items.splice(key, 1);
};

const completeItems = (index) => {
  listItems.value[index].completed = true;
};
</script>

<template>
  <div class="container">
    <input class="section" placeholder="To-Do" type="text" />

    <input
      class="toDoInput"
      placeholder="Add a To-Do"
      type="text"
      v-model="todo"
    />
    <button @click="AddToList">Add</button>

    <ul>
      <ToDoListItem
        v-for="(item, index) in listItems"
        :key="index"
        :task="item.task"
        :completed="item.completed"
        @complete="completeItems(index)"
      >
      </ToDoListItem>
    </ul>
  </div>
</template>

<style scoped>
.section {
  font-size: 17px;
  display: flex;
  border: solid 1px black;
  margin-left: 0;
  justify-content: center;
  text-align: center;
  width: 110px;
  border-radius: 10px;
}

.container {
  display: flex;
  flex-direction: column;
  align-content: center;
  align-items: center;
  background: rgb(49, 67, 91);
  width: 200px;
  border-radius: 10px;
  justify-content: flex-start;
  gap: 10px;
  padding-top: 10px;
  overflow-y: scroll;
  height: 350px;
}

.toDoInput {
  display: flex;
  align-items: center;
  align-content: center;
  justify-content: flex-end;
  width: 50%;
}

ul {
  display: flex;
  margin-right: 33px;
  flex-direction: column;
  max-width: fit-content;
  text-align: center;
  align-items: center;
}
</style>

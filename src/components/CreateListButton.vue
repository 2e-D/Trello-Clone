<script setup>
import { ref } from "vue";

const listTitle = ref("");

const emit = defineEmits(["addList"]);

const addList = () => {
  emit("addList", listTitle.value);
};
</script>
<template>
  <div class="addList">
    <input
      class="box"
      type="text"
      v-model="listTitle"
      placeholder="Add a list name"
    />
    <button @click="addList">Add new list</button>
  </div>
</template>

<style scoped>
.addList {
  display: flex;
  flex-direction: row;
  justify-content: center;
  align-items: center;
  text-align: center;
}

.box {
  width: 100px;
}
</style>

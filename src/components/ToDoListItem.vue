<script setup>
import Remove from "./icons/Remove.vue";
import { ref } from "vue";
import Modal from "./Modal.vue";
const emit = defineEmits(["delete-item"]);
const props = defineProps({
  task: {
    type: String,
  },
  completed: {
    type: Boolean,
  },
});

const isModalOpen = ref(false);

let openModal = () => {
  isModalOpen.value = true;
};

const closeModal = () => {
  isModalOpen.value = false;
};
</script>

<template>
  <div class="li-container">
    <li v-if="props.completed">
      <a class="link" href="#" @click="openModal">{{ props.task }}</a>
      <Modal :open="isModalOpen" @close="closeModal"
        ><h1>{{ props.task }}</h1>
        <input type="text class=editor-text" />
      </Modal>
    </li>

    <li v-else>
      <a class="link" href="#" @click="openModal">{{ props.task }}</a>
      <Modal :open="isModalOpen" @close-modal="closeModal"
        ><h1>{{ props.task }}</h1></Modal
      >
    </li>
  </div>
</template>

<style scoped>
li {
  list-style-type: none;
  margin: 10px;
  color: green;
  background: rgb(3, 192, 255);
  height: 25px;
  padding: 10px;
  border-radius: 60px;
  border-style: ridge;
}

.link {
  text-decoration: none;
  padding: 10px;
}

.li-container {
  display: flex;
}

.completed {
  text-decoration: line-through;
}
</style>

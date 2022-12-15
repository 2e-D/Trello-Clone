<script setup>
import Remove from "./icons/Remove.vue";
const emit = defineEmits(["close-modal"]);
const props = defineProps({
  open: {
    type: Boolean,
    default: false,
  },
});

const close = () => {
  emit("close-modal");
};
</script>

<template>
  <div v-if="open" class="modal-background" @click="$emit('close')">
    <div class="modal">
      <div class="modal-heading">
        <slot></slot>
        <Remove @click="close"></Remove>
        <input type="text" placeholder="Add information about this task" />
      </div>
      <div class="modal-body"></div>
    </div>
  </div>
</template>

<style scoped>
.modal-background {
  background: rgba(0, 0, 0, 0.5);
  width: 100%;
  height: 100vh;
  position: fixed;
  display: flex;
  justify-content: center;
  left: 0;
  z-index: 50;
  top: 0;
}

.modal {
  background: white;
  padding: 10px;
  color: black;
  width: 300px;
  height: 300px;
  display: flex;
  justify-content: center;
  align-items: center;
  margin-top: 15%;
  border-radius: 30px;
  flex-wrap: wrap;
}

.modal-heading {
  display: flex;
  flex-direction: column;
  gap: 20px;
  position: relative;
}
</style>

<script setup></script>

<template>
  <footer id="footer">
    <p>This project was created by Dan Toohey using VUE 3</p>
  </footer>
</template>

<style scoped>
#footer {
  color: black;
  display: flex;
  border: solid 2px blue;
  position: fixed;
  bottom: 0;
  width: 100%;
  height: 30px;
  font-size: 15px;
  justify-content: center;
  align-items: center;
  background-color: #e1f7f5;
  cursor: pointer;
  z-index: 50;
}
</style>

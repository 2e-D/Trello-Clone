<script setup></script>

<template>
  <header id="header">
    <p class="Htitle">
      Mello <span class="innerTxt">(Dans trello Clone)</span>
    </p>
  </header>
</template>

<style scoped>
#header {
  color: black;
  display: flex;
  border: solid 2px blue;
  position: fixed;
  top: 0;
  width: 100%;
  height: 30px;
  font-size: 20px;
  justify-content: flex-start;
  align-items: center;
  background-color: #e1f7f5;
  cursor: pointer;
  z-index: 50;
}

.innerTxt {
  font-size: 10px;
  font-family: Cambria, Cochin, Georgia, Times, "Times New Roman", serif;
  margin-left: -10px;
}

.Htitle {
  margin-left: 25px;
}

#header:hover {
  font-size: 25px;
}
</style>

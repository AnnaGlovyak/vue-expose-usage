<script setup>
import { ref } from "vue";
// import Modal from "./components/script_setup/Modal.vue";
// import Modal from "./components/options_api/Modal.vue";
import Modal from "./components/jsx/Modal.jsx";
import Menu from "./components/menu/Menu.vue";
import MenuButton from "./components/menu/MenuButton.vue";
import MenuItems from "./components/menu/MenuItems.vue";
import MenuItem from "./components/menu/MenuItem.vue";

const modal = ref(null);
const selected = ref("");
const menuItems = ["Edit", "Update", "Add"]
</script>

<template>
  <button @click="modal.open()">Outside open modal</button>
  <Modal ref="modal" />
  <Menu v-model="selected">
    <MenuButton>{{ 'Actions' }}</MenuButton>
    <MenuItems v-for="item in menuItems" :key="item">
      <MenuItem>
        <span :class="{active: item === selected}">{{ item }}</span>
      </MenuItem>
    </MenuItems>
  </Menu>
</template>

<style scoped>
.logo {
  height: 6em;
  padding: 1.5em;
  will-change: filter;
  transition: filter 300ms;
}

.logo:hover {
  filter: drop-shadow(0 0 2em #646cffaa);
}

.logo.vue:hover {
  filter: drop-shadow(0 0 2em #42b883aa);
}

.container {
  display: flex;
  width: 100%;
  /* flex-direction: column; */
}

.left {
  flex: 1
}

.right {
  flex: 1
}
</style>

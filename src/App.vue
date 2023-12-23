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
</script>

<template>
  <button @click="modal.open()">Outside open modal</button>
  <Modal ref="modal" />
  <Menu v-slot="{open, close}">
    <MenuButton>{{ 'Actions' }}</MenuButton>
    <MenuItems>
      <MenuItem v-slot="{active}">
        <span :class="{active}">Edit</span>
      </MenuItem>
      <MenuItem v-slot="{active}">
        <span :class="{active}">Update</span>
      </MenuItem>
      <MenuItem v-slot="{active}">
        <span :class="{active}">Add</span>
      </MenuItem>
      <MenuItem v-slot="{active}">
        <span :class="{active}" @click="close">Close</span>
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

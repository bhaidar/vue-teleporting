<template>
  <Modal @close-modal="closeModal">
    <template #body>
      <p>Lorem ipsum dolor sit amet, consectetur adipisicing elit. Repudiandae expedita corrupti laudantium aperiam, doloremque explicabo ipsum earum dicta saepe delectus totam vitae ipsam doloribus et obcaecati facilis eius assumenda, cumque.</p>
      <p>Lorem ipsum dolor sit amet, consectetur adipisicing elit. Repudiandae expedita corrupti laudantium aperiam, doloremque explicabo ipsum earum dicta saepe delectus totam vitae ipsam doloribus et obcaecati facilis eius assumenda, cumque.</p>
    </template>
  </Modal>
</template>

<script>
import Modal from "./components/Modal.vue";

export default {
  name: "App",
  components: {
    Modal,
  },
  methods: {
    closeModal() {
      alert("Clicked!");
    },
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>

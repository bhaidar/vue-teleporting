<template>
  <div>
    <h1>Demonstrating Teleporting in Vue 3</h1>
    <teleport to="#modal-area" :disabled="shouldClose" v-if="!shouldClose">
      <Modal @close-modal="closeModal">
        <template #body>
          <p>Lorem ipsum dolor sit amet, consectetur adipisicing elit. Repudiandae expedita corrupti laudantium aperiam, doloremque explicabo ipsum earum dicta saepe delectus totam vitae ipsam doloribus et obcaecati facilis eius assumenda, cumque.</p>
          <p>Lorem ipsum dolor sit amet, consectetur adipisicing elit. Repudiandae expedita corrupti laudantium aperiam, doloremque explicabo ipsum earum dicta saepe delectus totam vitae ipsam doloribus et obcaecati facilis eius assumenda, cumque.</p>
        </template>
      </Modal>
    </teleport>
  </div>
</template>

<script>
import Modal from "./components/Modal.vue";

export default {
  name: "App",
  components: {
    Modal,
  },
  data() {
    return {
      shouldClose: false,
    };
  },
  methods: {
    closeModal() {
      this.shouldClose = true;
    },
  },
};
</script>

<style>
h1 {
  text-align: center;
}
</style>

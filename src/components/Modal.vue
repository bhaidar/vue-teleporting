<template>
  <div>
    <div class="modal-overlay" id="modal-overlay"></div>
    <div
      class="modal"
      id="modal"
      role="dialog"
      aria-labelledby="modal-header"
      aria-describedby="modal-body"
    >
      <button
        class="close-button"
        id="close-button"
        aria-label="Close modal"
        @click.prevent="closeModal"
      >X</button>
      <div class="modal-container">
        <header class="modal-header" id="modal-header">
          <slot name="header">Header goes here ...</slot>
        </header>

        <section class="modal-body" id="modal-body">
          <slot name="body">Body goes here ...</slot>
        </section>

        <footer class="modal-footer">
          <slot name="footer">Footer goes here ...</slot>
        </footer>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "Modal",
  methods: {
    closeModal() {
      this.$emit("close-modal");
    },
  },
};
</script>

<style>
.modal {
  /* This way it could be display flex or grid or whatever also. */
  display: block;

  /* Probably need media queries here */
  width: 600px;
  max-width: 100%;

  height: 400px;
  max-height: 100%;

  position: fixed;

  z-index: 100;

  left: 50%;
  top: 50%;

  /* Use this for centering if unknown width/height */
  transform: translate(-50%, -50%);

  /* If known, negative margins are probably better (less chance of blurry text). */
  /* margin: -200px 0 0 -200px; */

  background: white;
  box-shadow: 0 0 60px 10px rgba(0, 0, 0, 0.9);
}

.modal-overlay {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  z-index: 50;

  background: rgba(0, 0, 0, 0.6);
}

.modal-container {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  overflow: auto;
  padding: 20px 50px 20px 20px;
}

.modal .close-button {
  position: absolute;

  /* don't need to go crazy with z-index here, just sits over .modal-guts */
  z-index: 1;

  top: 10px;

  /* needs to look OK with or without scrollbar */
  right: 20px;

  border: 0;
  background: black;
  color: white;
  padding: 5px 10px;
  font-size: 1.3rem;

  border-radius: 5px;

  cursor: pointer;
}

.modal-header {
  padding-bottom: 20px;
  text-transform: uppercase;
}

.modal-footer {
  position: fixed;
  left: 0;
  right: 0;
  bottom: 0;

  padding: 0 20px 20px;

  text-transform: uppercase;
}
</style>
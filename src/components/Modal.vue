<template>
  <div class="backdrop">
    <div class="modal" id="modal">
    <button class="close-btn" @click="$emit('toggleModal')">X</button>
      <p class="modal-text">Modal Content</p>
    </div>
  </div>
</template>

<script>
export default {
  emits: ["toggleModal"],
};
</script>

<style>
.modal {
  width: 100%;
  height: 100%;
  padding: 20px;
  margin-left: 10%;
  margin-top: 10px;
  background: rgba(101, 103, 131, 0.85);
  border-radius: 0px;
  border-left: 2px solid rgba(65, 69, 109, 0.85);
  border-top: 2px solid rgba(65, 69, 109, 0.85);
  transition: all 0.5s ease-in-out;
}
.modal-text {
  color: white;
  font-weight: bold;
}
.backdrop {
  top: 0;
  position: fixed;
  background: rgba(255, 255, 255, 0.5);
  width: 100%;
  height: 100%;
}
.close-btn {
  border: none;
  font-weight: bold;
  font-size: 1.5em;
  margin-left: 10%;
  background: transparent;
  position: absolute;
  top: 0;
  left: 0;
  padding: 0.5em;
}
</style>
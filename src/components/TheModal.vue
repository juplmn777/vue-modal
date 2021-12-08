<template>
  <div class="backdrop" @click.self="closeModal">
    <div class="modal">
      <span class="toggle-btn" @click="closeModal">X</span>
      <slot>default content</slot>
      <div class="actions">
        <slot name="links"></slot>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  emits: ['close'],
  methods: {
    closeModal() {
      this.$emit('close');
    },
  },
};
</script>

<style>
.backdrop {
  position: fixed;
  top: 0;
  background: rgba(0, 0, 0, 0.5);
  width: 100%;
  height: 100%;
  display: flex;
  align-items: center;
  justify-content: center;
}

.modal {
  position: relative;
  width: 40rem;
  padding: 2rem;
  margin: 100px auto;
  background: #fff;
  border-radius: 10px;
}

.modal .toggle-btn {
  position: absolute;
  top: 2rem;
  right: 2rem;
  font-size: 1.5rem;
  font-weight: bold;
  cursor: pointer;
}

.modal h2 {
  font-size: 3rem;
  color: #056674;
}

.modal .actions {
  display: flex;
  justify-content: center;
  align-items: center;
  gap: 2rem;
}

.modal .actions a {
  font-size: 1.5rem;
  color: #056674;
  text-decoration: none;
  border: 1px solid #056674;
  padding: 0.5rem 1rem;
  border-radius: 5px;
  transition: 0.5s;
}

.modal .actions a:hover {
  background: #056674;
  color: #fff;
  border: 1px solid #056674;
}
</style>

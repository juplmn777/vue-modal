<template>
  <h1>{{ mainTitle }}</h1>
  <p>{{ text }}</p>
  <div v-if="showModal">
    <TheModal @close="toggleModal">
      <template v-slot:links>
        <a href="#">sign up now</a>
        <a href="#">More infos</a>
      </template>
      <h2>Hello from Vue 3</h2>
      <p>Learning Vue seems cool !</p>
    </TheModal>
  </div>

  <div v-if="showSecondModal">
    <TheModal @close="toggleSecondModal">
      <h2>Learn it now !!!</h2>
      <p>Become a Vue Developer</p>
    </TheModal>
  </div>
  <div class="buttons">
    <button @click="toggleModal" class="btn-modal-one">open Modal 1</button>
    <button @click="toggleSecondModal" class="btn-modal-two">
      open Modal 2
    </button>
  </div>
</template>

<script>
import TheModal from './components/TheModal.vue';

export default {
  name: 'App',
  components: {
    TheModal,
  },
  data() {
    return {
      mainTitle: 'Vue Modal',
      text: 'Welcome...',
      showModal: false,
      showSecondModal: false,
    };
  },
  methods: {
    toggleModal() {
      this.showModal = !this.showModal;
    },
    toggleSecondModal() {
      this.showSecondModal = !this.showSecondModal;
    },
  },
};
</script>

<style>
#app {
  font-family: Arial, Helvetica, sans-serif;
  text-align: center;
  color: #333;
  margin-top: 60px;
}

body {
  font-size: 62.5%;
}

h1 {
  font-size: 4rem;
}

p {
  font-size: 1.5rem;
}

.buttons {
  padding: 2rem;
  display: flex;
  justify-content: center;
  align-items: center;
  gap: 2rem;
}

button {
  padding: 1rem;
  border-radius: 5px;
  border: 1px solid #fff;
  cursor: pointer;
  color: #fff;
  text-transform: uppercase;
  font-weight: bold;
  transition: all 0.5s;
}

.btn-modal-one {
  background: #ff4b5c;
}

.btn-modal-one:hover {
  background: #fff;
  color: #ff4b5c;
  border: 1px solid #ff4b5c;
}

.btn-modal-two {
  background: #056674;
}

.btn-modal-two:hover {
  background: #fff;
  color: #056674;
  border: 1px solid #056674;
}
</style>

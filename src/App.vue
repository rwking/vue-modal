<template>
  <h1>{{ title }}</h1>
  <br />
  <!-- <p><input type="text" ref="name"></p> -->
  <p><button @click="toggleModal">Toggle modal</button></p>
  <transition name="slide" :duration="500">
      <Modal v-if="showModal" @toggleModal="toggleModal" />
  </transition>
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
      title: "Demonstration of modal pop-out",
      showModal: false,
    };
  },
  methods: {
    toggleModal() {
      console.log(this.$refs.name);
      //   this.$refs.name.classList.remove('input-gray')
      //   this.$refs.name.focus()
      this.showModal = !this.showModal
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
h1 {
  border-bottom: 1px solid #dddd;
  display: inline-block;
  padding-bottom: 10px;
}
.input-gray {
  background-color: rgb(199, 199, 199);
}
.slide-enter, .slide-leave-active {
  right: -100%;
  transition: all .8s;
}


/* General styles unrelated to slide in */
body {
  font-family: "Mulish", sans-serif;
}

.toggle {
  margin: 1em;
}

button {
  padding: 0.5em 1em;
  border-radius: 3em;
  font-size: 1.1em;
}

h1 {
  font-weight: 200;
}
</style>

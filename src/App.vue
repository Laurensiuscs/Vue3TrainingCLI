<template>
  <h1>{{ title }}</h1>
  <p>welcome</p>
  <div v-if="showModal">
    <!-- <Modal :header="header" :text="text" theme="sale" @tutup="toggleModal" /> -->
    <modal theme="sale" @tutup="toggleModal">
      <template v-slot:links>
        <a href="#">test link</a>
      </template>
      <h1>Register here</h1>
      <p>please register first</p>
    </modal>
  </div>

  <div v-if="showModalTwo">
    <modal @tutup="toggleModaltwo">
      <h1>Challenge Accepted!</h1>
      <p>The challenge has beed completed</p>
    </modal>
  </div>
  <!-- <input type="text" ref="nama" /> -->
  <button @click.shift="toggleModal">Open Modal (shift)</button>
  <button @click.alt="toggleModaltwo">Open Modal 2 (alt)</button>
</template>

<script>
import Modal from "./components/Modal.vue";
// import HelloWorld from './components/HelloWorld.vue'

export default {
  name: "App",
  components: { Modal },
  data() {
    return {
      title: "my fist Vue",
      header: "Sign Up",
      text: "Please register here",
      showModal: false,
      showModalTwo: false,
    };
  },
  methods: {
    handleClick() {
      console.log(this.$refs.nama);
      this.$refs.nama.classList.add("active");
      this.$refs.nama.focus();
    },
    toggleModal() {
      this.showModal = !this.showModal;
    },
    toggleModaltwo() {
      this.showModalTwo = !this.showModalTwo;
    },
  },
  /* components: {
    HelloWorld
  } */
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
  border-bottom: 1px solid #ddd;
  display: inline-block;
  padding-bottom: 10px;
}
</style>

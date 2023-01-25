<template>
  <h1>{{ title }}</h1>
  <p>Welcome...</p>
  <teleport to="#modals" v-if="showModal">
    <Modal theme="sale" @close="toggleModal">
      <template v-slot:links>
        <a href="#">sign up now</a>
        <a href="#">more infor</a>
      </template>
        <h1>Summer Giveaway</h1>
        <p>Grab your favourite Tshirt for half Price!</p>
    </Modal>
  </teleport>
  <teleport to="#modals" v-if="showModalTwo">
    <Modal @close="toggleModalTwo">
      <template v-slot:buttons>
        <a href="#">Subscribe</a>
        <a href="#">Buy Now</a>
      </template>
      <h1>Buy our lates Products!</h1>
      <p>Minimalistic Design and great user experience</p>
    </Modal>
  </teleport>
  <button @click.alt="toggleModal">open modal (alt)</button>
  <button @click ="toggleModalTwo">Open Modal Two (shift)</button>
</template>

<script>
import Modal from './components/Modal.vue'


export default {
  name: 'App',
  components: { Modal },
  data() {
    return {
      title: "My First Vue App",
      showModal: false,
      showModalTwo: false
    }
  },
  methods: {
    toggleModal(){
      this.showModal = !this.showModal
    },
    toggleModalTwo(){
      this.showModalTwo = !this.showModalTwo
    }
  }
}
</script>

<style>
#app, #modals {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

</style>

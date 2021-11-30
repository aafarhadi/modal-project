<template>
  <h1>{{ title }}</h1>
  <p>welcome...</p>
  <div v-if="showModal">
    <Modal :header="header" :text="text" theme="sale" @close="toggleModal" >
      <p> ini dikirim dari slot</p>
      <template v-slot:links>
        <a href="#">sign up</a> 
        <a href="#">more info</a> 
      </template>
     
    </Modal>
  </div>

  <div v-if="showModalTwo">
    <Modal @close="toggleModalTwo" >
      <h1>Ninja Giveaway 2</h1>
      <p>Grab your ninja swag for half price </p>
    </Modal>
  </div>



  <button @click="toggleModal">open modal</button> 
  <button @click="toggleModalTwo">open modal two</button> 
</template>

<script>
import Modal from './components/Modal.vue'

export default {
  name: 'App',
  components: { Modal },
  data() {
    return {
      title: 'first vue app',
      showModal: false,
      showModalTwo: false,
    } 
  },
  methods: {
    toggleModal() {
      this.showModal = !this.showModal
    },
    toggleModalTwo() {
      this.showModalTwo = !this.showModalTwo
    }
  }

}
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
h1{
  border-bottom: 1px solid #ddd;
  display: inline-block;
  padding-bottom: 10px;
}
</style>

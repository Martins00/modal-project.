<template> 
  <h1> {{ title }}</h1>
  <div v-if="showModal">
    <Modal :content="content" :warning="warning" :header="header" theme="sale" @close='(displayModal)'>
      <h1>{{header}}</h1>
      <p>{{warning}}</p>
    </Modal>
  </div> 

   <div v-if="showModalTwo">
    <Modal @close='(displayModalTwo)'>
      <h1>Welcome...</h1>
      <p>Are you ready?</p>
    </Modal>
  </div> 
  <input type="text" ref="name">
  <button @click="handleClick">Click Me</button> <br> <br>
  <button @click="displayModal">DO NOT CLICK THIS</button>
  <button @click="displayModalTwo">CLICK TO CONTINUE</button>
</template>

<script>
import Modal from './components/Modal.vue'

export default {
  name: 'App',
  components: {Modal},
  data() {
    return {
      title: "Learning Vue By Building",
      warning: "Last Warning",
      content: 'This is my very first vue app',
      header: 'Do not click that again',
      showModal: false,
      showModalTwo: false
    }
  }, 
  methods: {
    handleClick() {
      console.log(this.$refs.name) 
      this.$refs.name.classList.add('active')
      this.$refs.name.focus()
    },
    displayModal () {
      this.showModal = !this.showModal
    },
    displayModalTwo () {
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
</style>

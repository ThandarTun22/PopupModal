<template>
  <h1>hi</h1>
  <div v-if="showModal">
    <Popup_Modal :theme="theme" @close="showModal=false">
        <h1>Login Success</h1>
        <p>Welcome user hlaing min than</p>
        <template v-slot:links>
            <a href="">Sign Up</a>
            <a href="">Register</a>
        </template>
    </Popup_Modal>

  </div>
  <div v-if="deleteModal">
    <Popup_Modal :themeDelete="themeDelete" @close="deleteModal=false">
      <h1>Delete</h1>
      <p>Are you sure want to delete?</p>
    </Popup_Modal>
  </div>
  
  <button @click="showModal = true">open modal</button>
  <button @click="deleteModal = true">Delete</button>
</template>

<script>
// import HelloWorld from './components/HelloWorld.vue'
import Popup_Modal from './components/Popup_Modal.vue'

export default {
  data(){
    return{
      theme : "success",
      showModal : false,
      themeDelete : "delete",
      deleteModal : false
    }
  },
  components: {
    Popup_Modal
  }
}
</script>

<style scoped>
  h1{
    color: blue;
  }
  p{
    font-style: normal;
  }
</style>

<template>
  <h1 ref="greeting"> Hello{{name}}</h1>
  <div v-if="showModal">
    <modal @close="showModal=false" :theme="theme">
      <h1>Login</h1>
      <p>Hi There</p>
      <template v-slot:links>
      <a href="">Google</a>
      <a href="">Google</a>
      </template>

    </modal>
  </div>
   <div v-if="showModal1">
    <modal @close="showModal1=false" :theme="theme2" >
      <h1>Delete</h1>
      <p>Hi There</p>
      <template v-slot:links>
      <a href="">Google</a>
      <a href="">Google</a>
      </template>

    </modal>
  </div>
  <button @click="showModal='true'"> show </button>
  <button @click="showModal1=true"> delete </button>
</template>

<script>
import Modal from './components/Modal.vue'

export default {
 data(){
  return{
   
    showModal:false,
    showModal1:false,
    theme:"success",
    theme2:"delete"
    
  }
 },
 components:{Modal}
 
 
}
</script>

<style scoped>
h1{
  color:white;
}
</style>
<template>
  <div class="backdrop" @click.self="closeModel"  >
    <div class="modal" :class="{success:theme==='success',danger:theme==='delete'}">
       
       <slot/>
         <slot name="links"/>
      
    </div>
  </div>
</template>

<script>
export default {
  props:['theme'],
  methods:{
    closeModel(){
        this.$emit("close")
    }
  }
}
</script>

<style>
 .backdrop{
    position:fixed;
    top: 0;
    background:rgba(0,0,0,0.5);
    width: 100%;
    height: 100%;

 }
 .modal{
 width: 400px;
 padding: 20px;
 margin: 100px auto;
 background-color: aliceblue;
 border-radius: 10px;

 }
 .success{
    background-color: green;
    color: white;
 }
 .danger{
    background-color: red;
    color: white;
 }

</style>
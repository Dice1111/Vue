<template>
  <h1 ref="greet">Hi</h1>
  <input type="text" ref="name">
  <button @click="clickHandler">click</button>
  <div v-if="showModal">
    <Modal :header="header" :content="content" :theme="theme" @close="showModal=false">
      <h1 style="color:white;">banana</h1>
      <p>apple</p>
    </Modal>
  </div>
<!-- ................................Homework.................................... -->
  <div v-if="showModal2">
    <Modal :header="header" :content="content" :theme="theme2" @close="showModal2=false">
      <h1 style="color:white;">Mango</h1>
      <p>Orange</p>
    </Modal>
  </div>
  <button @click="showModal=true">open modal</button>
  <button @click="showModal2=true">Delete</button>

</template>

<script>

import Modal from "./components/Modal-Box.vue"

export default {
  data(){
    return{
      title:'Happy',
      header:'Login success',
      content:'Welcome user apple',
      theme:'success',
      theme2:'danger',
      showModal:false,
      showModal2:false
    }
  },
  methods:{
    clickHandler(){
      this.$refs.name.focus();
      this.$refs.greet.textContent="Greeting";
    }
  },
  components:{
    Modal:Modal
  }
};
</script>

<style scoped>
  h1{
    color: red;
  }
</style>

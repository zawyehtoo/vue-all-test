<template>
  <h2>{{title}}</h2>
  <p>Welcome</p>
  <teleport to='#modal' v-if='showModal' >
  <Modal  theme="sale" @close='toggleModal'>
      <h2>Sign up for the app</h2>
      <p>testing</p>
      <template v-slot:links>
          <a href="#">Sign up</a>
          <a href="#">More info</a>
      </template>
  </Modal>
  </teleport>
  <teleport to='#modal' v-if='showModalTwo'>
     <Modal  theme="" @close='toggleModalTwo'>
      <h2>Hi I'm the another Modal</h2>
      <p>testing2</p>

      <template v-slot:links>
          <a href="#">Sign up</a>
          <a href="#">More info</a>
      </template>
  </Modal>
  </teleport>
 <button @click='toggleModal'>open</button>
 <button @click='toggleModalTwo'>open second component</button>
</template>

<script>
import Modal from './components/Modal.vue'

export default {
  name: 'App',
  components:{Modal},
  data(){
    return{
        title:'My first Vue App',
        showModal:false,
        showModalTwo:false,
    }
   
  },
  methods:{
     toggleModal(){
      this.showModal=!this.showModal
     },
     toggleModalTwo(){
      this.showModalTwo=!this.showModalTwo
     },
  
    }
}
</script>

<style >
#app ,#modal{
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
h2{
  color: aqua;
}

</style>

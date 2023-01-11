<script setup>
import Invoice from './components/Invoice.vue'
import {ref} from 'vue'
const invoiceToggle = ref(false)

const buttonHandler = () => {
  invoiceToggle.value = !invoiceToggle.value
}
</script>

<template>
  <div class="main">
       <div class="btn no-print">
        <button v-if="invoiceToggle===false" @click="buttonHandler">View Invoice</button> 
        <button v-if="invoiceToggle===true" @click="buttonHandler">Hide Invoice</button>
       </div>
       <Invoice v-if="invoiceToggle===true" />
  </div>

</template>

<style scoped>
.btn{
  text-align: center;
  margin-top: 20px;
}
button{
  width:120px;
  padding: 10px;
  background-color: rgb(10, 10, 78);
  color: white;
  font-size: 15px;
  font-weight: bold;
}
button:hover{
  border:1px solid rgb(10, 10, 78);
  color: rgb(95, 22, 22);
  background-color: white;
  cursor: pointer;
  width:120px;
  padding: 10px;
}
.main{
  margin-bottom: 30px;
}
</style>

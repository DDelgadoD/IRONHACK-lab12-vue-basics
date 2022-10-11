<template>
  <div class="container">
    <Navbar />
    <div class="border border-dark my-2 p-2">
      <h4>ITERATION 2</h4>
      <div>2 + 2 son {{2 + 2}}</div>

      <div> {{setter()}}</div>
    </div>

    <div class="border border-dark my-2 p-2">
      <h4>ITERATION 3</h4>

      <div class="border border-dark my-2 mx-5 ">
        <div v-show="showIt">Now "showIt" == true </div>
        <div v-if="ifIt">Now "ifIt" == true</div>
      </div>
      <div class="d-flex justify-content-end ">      
        <button class="btn btn-success m-2" @click="ifAndHide()">If and Hide</button>
        <button class="btn btn-warning m-2 me-5" @click="showAndHide()">Show and Hide</button>
      </div>  
    </div>

    <div class="border border-dark my-2 p-2" >
      <h4>ITERATION 4</h4>
      <div v-for="greeting in greetings" key="greeting">
        <li>{{greeting}}</li>
      </div>
    </div>

    <div class="border border-dark my-2 p-2">
      <h4>ITERATION 5</h4>
      <div :class=bg >COLOR CHANGE</div>
      <div class="d-flex justify-content-end ">    
        <button class="btn btn-info m-2 me-5" @click="changeColor()">Change</button>
      </div>
    </div>
    <Footer />
  </div>
</template>

<script setup>
import Navbar from './components/Navbar.vue';
import Footer from './components/Footer.vue';
import { ref } from "vue";

const setter = () => {
  return "Hello from function"
}

const showIt = ref(true);
const ifIt = ref(false);

const showAndHide = () => {
  showIt.value = !showIt.value;
}

const ifAndHide = () => {
  ifIt.value = !ifIt.value;
}

const greetings = ref([
  "Hola",
  "Hello",
  "Hi",
  "Hey",
  "Bon Jour"
]);

const bg = ref(["bg-warning","m-5", "my-2", "p-5"]);

const changeColor = () => {
  console.log(bg.value[0])
  bg.value[0] == 'bg-danger'
  ? bg.value =["bg-warning","mx-5", "my-2", "p-5"]
  : bg.value =["bg-danger","mx-5", "my-2", "p-5"];
 
}

</script>

<style scoped>

</style>
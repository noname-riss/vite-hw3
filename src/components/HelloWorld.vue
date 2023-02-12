<template>
 
<!--TESTING-->

<div class="card">
  <img class="image" src="https://www.psu.edu/PSU-mark-navy.jpg"/>
  <h1>Penn State Hax</h1>
  
  <p> Here is the class website for IST 256 and Haxpsu:
  <a href="https://hax.psu.edu/">

  </a> </p>
    <button class="button">
      Details
  </button>
   
  </div>

<div class="buttonHolder">
    <button class="add" v-on:click="duplicate"> Add Frame </button>

  <button class="chageBG" v-on:click="changeBackGround">Change Background</button>

   <button class="chageti" v-on:click="changetitle">Change Title</button>

  <button class="delete" v-on:click="deleteLast">Delete last card</button>
</div>

 

</template>

<script setup>
import { defineProps, reactive } from 'vue'

defineProps({
  msg: String
})

const state = reactive({ count: 0 })
</script>


<script>
export default {

  methods: {
    duplicate(){
     
  const itemToClone = document.querySelector('.card').cloneNode(true);
  document.body.appendChild(itemToClone);
},
    
changetitle(){
 
  let name = prompt('Name: ');
  if (name) {
    document.querySelector('.card h1').innerText = name;
  }
},
changeBackGround(){

  document.querySelectorAll('.card').forEach((item, index) => {
    if (!item.classList.contains('newBG')) {
      item.classList.add('newBG');
    }
    else {
      item.classList.remove('newBG');
    }
  });
},

deleteLast(){
  
  let wantsTo = confirm("Are you sure?");
  if (wantsTo) {
    if (document.querySelector('.card:last-child') !== document.querySelector('.card')) {
      document.querySelector('.card:last-child').remove();      
    }
    else {
      alert("Can't delete last card!");
    }
  }
}
}
  }

</script>




<style scoped>
.card{
    border: 10px solid rgb(8, 8, 8);
    background-color: blue;
    display: flex;
    margin: 82px auto 32px;
    padding: 0 16px;
    max-width: 400px;
    flex-direction: column;
    align-items: center;
  }
.image{
  visibility: visible;
  width: 400px;
}

  .buttonHolder{
    text-transform: uppercase;
    padding: 8px;
    flex-direction: column;
    align-items: center;
  }

  .card:hover{
  background-color:grey;
}

.newBG{
  background-color:white;
}
</style>

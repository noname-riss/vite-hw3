<template>
 
<!--TESTING-->
<div class="card">
  <img src="https://www.psu.edu/PSU-mark-navy.jpg" width=400/>
  <h1>Penn State Hax</h1>
  <p> Here is the class website for IST 256 and Haxpsu:
  <a href="https://hax.psu.edu/">

  </a> </p>
    <button class="button">
      Details
  </button>
  <div class="buttonHolder">
    <button class="toggle"> Add Frame </button>

  <button class="chageBG">Change Background</button>

   <button class="chageti">Change Title</button>

  <button class="delete">Delete last card</button>
</div>
  </div>
</template>

<script setup>
import { defineProps, reactive } from 'vue'

defineProps({
  msg: String
})

const state = reactive({ count: 0 })
</script>

<style scoped>
.card{
    border: 10px solid blue;
    background-color: blue;
    display: flex;
    margin: 82px auto 32px;
    padding: 0 16px;
    max-width: 960px;
    flex-direction: column;
    align-items: center;
  }


  .buttonHolder{
    text-transform: uppercase;
    padding: 8px;
    flex-direction: column;
    align-items: center;
  }
</style>

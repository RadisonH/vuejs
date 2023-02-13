<template>
  <h1>{{ msg }}</h1>

<div class="card" style="width: 400px;">
  <h2 class="card-title">Let Him Cook!</h2>
  <img src="https://i.kym-cdn.com/entries/icons/facebook/000/041/943/1aa1blank.jpg" alt="image" style="width: 70%; height: auto;">
  <p class="card-description">Woody holding Sora back to let someone cook</p>
  <button class="dup-button" id="dup-imgbutton">Duplicate Card</button>
  <button class="toggle-button" id="toggle-imgbutton">Toggle Color</button>
  <button class="changeText-button" id="changeText-imgbutton">Change Text</button>
  <button class="del-button" id="del-imgbutton">Delete</button>
  <button class="details-button" id="details-imgbutton">Details</button>
</div>


  <p>
    <a href="https://vitejs.dev/guide/features.html" target="_blank">
      Vite Documentation
    </a>
    |
    <a href="https://v3.vuejs.org/" target="_blank">Vue 3 Documentation</a>
  </p>

  <button type="button" @click="state.count++">count is: {{ state.count }}</button>
  <p>
    Edit
    <code>components/HelloWorld.vue</code> to test hot module replacement.
  </p>
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
    hoover() {
      document.querySelectorAll(".card").forEach((item) => {
        if(!item.classList.contains("hoverCard")){
          item.classList.add("hoverCard");
          console.log(item);
        }
        else{
          item.classList.remove("hoverCard");
          console.log(item);
        }
      });
    },
    
    duplicate() {
      const cloneCard = document.querySelector(".card").cloneNode(true);
      document.body.appendChild(cloneCard);
      console.log(cloneCard);    
    },

    background() {
      document.querySelectorAll(".card").forEach((item) => {
        if(!item.classList.contains("basic")){
          item.classList.add("basic");
          console.log(item);
        }
        else{
          item.classList.remove("basic");
          console.log(item);
        }
      });
    },

    

    //Kinda borked rn
    deleter(){
      document.querySelector(".card:last-child").remove();
      console.log(card);
    }
  }
}
</script>

<style scoped>
a {
  color: #42b983;
}
</style>

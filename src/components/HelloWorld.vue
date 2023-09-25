<script setup>
import { ref } from 'vue'

defineProps({
  msg: String,
})

const count = ref(0)

document.querySelector('.details').addEventListener('click', (e) => {
  const crd = document.querySelector('.card p');
  const disp = crd.style.display;
  
  if (disp === 'none') {
    crd.style.display = 'block';
  } else {
    crd.style.display = 'none';
  }
});

</script>

<template>
  <h1>{{ msg }}</h1>

  <div class="card">
    <button type="button" @click="count++">count is {{ count }}</button>
    <p>
      Edit
      <code>components/HelloWorld.vue</code> to test HMR
    </p>
  </div>

  <p>
    Check out
    <a href="https://vuejs.org/guide/quick-start.html#local" target="_blank"
      >create-vue</a
    >, the official Vue + Vite starter
  </p>
  <p>
    Install
    <a href="https://github.com/johnsoncodehk/volar" target="_blank">Volar</a>
    in your IDE for a better DX
  </p>
  <p class="read-the-docs">Click on the Vite and Vue logos to learn more</p>

  <div class="card">
    <div class="title">
      <h2>This is the Title of a Card</h2>
    </div>

    <div class="image">
      <img src="https://icon-library.com/images/default-user-icon/default-user-icon-13.jpg"
           alt="user icon"
           width="400"
           >
      <p>Description of the image above. Lorem ipsum dolor sit amet.</p>
    </div>
    
    <button class='details'>
      <a>Details</a>
    </button>
  </div>

</template>

<style scoped>
.read-the-docs {
  color: #888;
}

.dupe:hover {
  background-color: black;
  color: white;
}

.dupe:focus {
  background-color: black;
  color: white;
}

.layout {
  display: flex;
  grid-template-columns: repeat(3, 1fr);
  gap: 10px;
  grid-auto-rows: minmax(100px, auto);
}

.card {
  border: 10px solid;
  margin: auto;
  width: 500px;
  padding: 10px;
  text-align: center;
  background-color: cyan;
}

.details {
    display: inline;
}

@media screen and (max-width: 800px) {
  .details {
    display: none;
  }
}

@media screen and (max-width: 500px) {
  .card {
    width = 100%;
  }
}

</style>

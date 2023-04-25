<script setup>
  import { ref } from 'vue';
  const count = ref(0);

  const addtoCount = () =>{
    console.log("addtoCount")
    count.value++
  }
  const subbtoCount = ()=>{
    console.log("subtoCount")
    count.value--

  }
</script>

<template>
  <main>
    <div>
      <h4>COUNTER IS CURRENTLY AT:</h4>
      <h1>{{ count }}</h1>
      <button @click="subbtoCount">-</button>
      <button @click="addtoCount">+</button>
    </div>
  </main>
</template>

<style scoped>
main {
    background-color: brown;
    height: 100vh;
    width: 100vw;
    display: flex;
    align-items: center;
    justify-content: center;
    text-align: center;
  }
  div {
    text-align: center;
  }
</style>

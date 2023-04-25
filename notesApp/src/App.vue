<script setup>

</script>

<template>
  <header>
    
  </header>

  <main>
  <div class="container">
    <header>
      <h1>Notes</h1>
      <button>+</button>
    </header>
    <div class="cards-container">
      <div class="card">
      <p class="main-text">Lorem ipsum dolor sit amet consectetur adipisicing elit. Mollitia, minus.
      </p>
      <p class="date">04/20/2023</p>
    </div>
    <div class="card">
      <p class="main-text">Lorem ipsum dolor sit amet consectetur adipisicing elit. Mollitia, minus.
      </p>
      <p class="date">04/20/2023</p>
    </div>
    </div>
  </div>
  </main>
</template>

<style scoped>
.main {
  height: 100vh;
  width: 100vw;
}

.container {
  max-width: 1000px;
  padding: 10px;
  margin: 0 auto;
}

header {
  display: flex;
  justify-content: space-between;

}

h1 {
  font-weight: bold;
  font-size: 75px;
  margin-bottom: 25px;
}

button {
  border: none;
  padding: 10px;
  width: 50px;
  height: 50px;
  cursor: pointer;
  background-color: black;
  border-radius: 100%;
  color: white;
  font-size: 20px;
}

.card{
  height: 225px;
  width: 225px;
  background-color:brown;
  padding: 10px;
  border-radius: 15px;
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  margin-right: 20px;
  margin-bottom: 20px;
}

.date{
  font-weight: bold;
  font-size: 15px;
}

.cards-container{
  display: flex;
  flex-wrap: wrap;
}
</style>

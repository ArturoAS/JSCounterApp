<script setup>
import { ref } from "vue";

const showModal = ref(false)
const newNote = ref("")
const notes = ref([])

function getRandomColor() {
  return "hsl(" + Math.random() * 360 + ", 100%, 75%)";
}

const addNote = () => {
  notes.value.push({
    id: Math.floor(Math.random() * 100000),
    text: newNote.value,
    date: new Date(),
    noteColor: getRandomColor()
  })
  showModal.value = false;
  newNote.value = "";
}
</script>

<template>
  <main>
    <div v-if="showModal" class="overlay">
      <div class="modal">
        <textarea v-model="newNote" name="note" id="note" cols="30" rows="10"></textarea>
        <button @click="addNote">Add Note</button>
        <button2 class="close" @click="showModal = false">Close</button2>
      </div>
    </div>
    <div class="container">
      <header>
        <h1>Notes</h1>
        <button @click="showModal = true">+</button>
      </header>
      <div class="cards-container">
        <div v-for="note in notes" class="card" :style="{ backgroundColor: note.noteColor }">
          <p class="main-text">{{ note.text }}
          </p>
          <p class="date">{{ note.date.toLocaleDateString("en-US") }}</p>
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

.card {
  height: 225px;
  width: 225px;
  background-color: brown;
  padding: 10px;
  border-radius: 15px;
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  margin-right: 20px;
  margin-bottom: 20px;
}

.date {
  font-weight: bold;
  font-size: 15px;
}

.cards-container {
  display: flex;
  flex-wrap: wrap;
}

.overlay {
  position: absolute;
  width: 100%;
  height: 100%;
  background-color: rgba(0, 0, 0, 0.77);
  transform: translate(-50%, -50%);
  top: 50%;
  left: 50%;
  display: flex;
  align-items: center;
  justify-content: center;
  z-index: 10;
}

main {
  height: 100vh;
  width: 100vw;
}


.modal {
  width: 750px;
  background-color: white;
  border-radius: 10px;
  padding: 30px;
  position: relative;
  display: flex;
  flex-direction: column;
}

.modal button {
  padding: 10px 20px;
  font-size: 20px;
  width: 100%;
  height: 100%;
  background-color: rgb(0, 122, 29);
  border: none;
  color: white;
  cursor: pointer;
  margin-top: 15px;
  border-radius: 0%;
}

.modal button2 {
  padding: 10px 20px;
  font-size: 20px;
  width: 100%;
  height: 100%;
  background-color: rgb(122, 8, 0);
  border: none;
  color: white;
  cursor: pointer;
  margin-top: 15px;
  border-radius: 0%;
  text-align: center;
}

.modal p {
  margin-left: auto;
  font-size: 20px;
  z-index: 100000;
  cursor: pointer;
}

textarea {
  width: 100%;
  height: 200px;
  padding: 5px;
  font-size: 20px;
}
</style>

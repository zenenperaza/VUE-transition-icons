<template>
<div> 
  <button v-on:click="addNotes">Add Note</button>
  <input type="text" v-model="note">
  <TransitionGroup name="list" tag="ul">
    <li v-for="note in notes" :key="note"> <v-icon name="pi-charizard-shiny"/> {{ note }} </li>
  </TransitionGroup>


</div>
</template>

<script lang="ts" setup>
import { ref } from "vue"
import { GiExitDoor } from "oh-vue-icons/icons";

const note = ref('')
const notes = ref([])

const addNotes = () => {
  notes.value.push(note.value)
  note.value = ''
}


</script>

<style scoped>
.list-enter-active, .list-leave-active{
transition: all 0.5s ease;
}
.list-enter-from, .list-leave-to{
opacity: 0;
transform: translateX(30px);
}
</style>

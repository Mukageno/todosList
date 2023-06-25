<template>
  <NavBar />
  <Notes />
  <Modal @addNote="addNote" @active="modalActive = false" v-show="modalActive" />
  <AddBtn @click="modalActive = !modalActive" />
</template>

<script>
import NavBar from './components/NavBar.vue';
import Notes from './components/Notes.vue';
import AddBtn from './components/AddBtn.vue';
import Modal from './components/Modal.vue';

export default {
  name: 'App',
  data() {
    return {
      modalActive: false,
      notes: []
    }
  },
  components: {
    NavBar,
    Notes,
    AddBtn,
    Modal
  },
  methods: {
    addNote(val) {
      let note = { val }
      this.notes.push(note)
      console.log(this.notes);
    }
  },
}
</script>

<style></style>

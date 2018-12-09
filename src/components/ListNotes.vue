<template>
  <div>
    <note v-on:delete-note="deleteNote" v-for="note in notes" :note.sync="note"></note>
  </div>
</template>

<script type = "text/javascript" >
  import Note from './Note';
  export default {
    props: ['notes'],
    components: {
      Note
    },
    methods: {
      deleteNote(note) {
        var removeIt = confirm('Do you really wanna remove it?');
        if (removeIt) {
          const noteIndex = this.notes.indexOf(note);
          this.notes.splice(noteIndex, 1);
          alert('Note deleted!');
        }
      },
    },
  };
</script>

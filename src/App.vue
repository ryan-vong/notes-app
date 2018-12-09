<template>
  <div id="app">
    <h1 class="ui centered header">Vue.js Notes App</h1>
    <div>
      <list-notes v-bind:notes="notes"></list-notes>
      <create-note v-on:create-note="createNote"></create-note>
    </div>
  </div>
</template>

<script>
  import ListNotes from './components/ListNotes';
  import CreateNote from './components/CreateNotes';
  export default {
    name: 'app',
    components: {
      ListNotes,
      CreateNote,
    },
    data() {
      return {
        notes: [{
          title: 'Lunch at 12PM',
          description: 'Call Robert to remember him.'
        }, {
          title: 'Gym with Jane',
          description: 'She is needing your motivation...'
        }, {
          title: 'Call mom',
          description: 'Ask her about the cats?'
        }],
      };
    },
    methods: {
      createNote(note) {
        this.notes.push(note);
        alert('Note created!');
      },
    },
  };
</script>

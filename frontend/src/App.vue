<template>
  <WordGrid :words="words"/>
  <Keyboard @keyPress="handleKeyPress"/>
</template>

<script>
import WordGrid from './components/WordGrid.vue'
import Keyboard from './components/Keyboard.vue'

export default {
  name: 'App',
  components: {
    WordGrid,
    Keyboard
  },
  data() {
    return {
      words: [
        ''
      ],
      activeWord: 0,
    }
  },
  methods: {
    handleKeyPress(payload) {
      console.log(payload, payload == '{bksp}')
      if (payload === '{enter}') {
        if (this.words[this.activeWord].length === 5) {
          this.words.push('');
          this.activeWord += 1;
          return;
        }
      }

      if (payload === '{bksp}') {
        const word = this.words[this.activeWord];
        const wordLength = word.length;

        if (wordLength > 0) {
          const newWord = word.slice(0, length - 1);
          this.words.splice(this.activeWord, 1, newWord);
        }

        return;
      }
      
      return this.words[this.activeWord] += payload;
    }
  },
  computed: {

  },
  watch: {

  },
}
</script>

<style>
body {
  height: 90vh;
  width: 90vw;
  display: flex;
  justify-content: center;
  align-items: center;
  margin: auto;
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
  height: 100%;
  width: 100%;
  display: flex;
  flex-direction: column;
  justify-content: space-between;
}
</style>

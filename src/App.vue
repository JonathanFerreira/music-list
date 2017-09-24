<template>
  <div id="app">
    <input-music @newMusic='addMusic'></input-music>
    <music-list :list='musics' @removeMusic='removeMusic'></music-list>
  </div>
</template>

<script>
import InputMusic from './components/InputMusic'
import MusicList from './components/MusicList'

export default {
  name: 'app',
  data () {
    return {
      musics: []
    }
  },
  components: {
    InputMusic,
    MusicList
  },
  methods: {
    addMusic (music) {
      this.musics.push(music)
    },
    removeMusic (index) {
      this.musics.splice(index)
    }
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>

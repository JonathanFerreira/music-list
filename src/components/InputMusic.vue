<template>
  <div>
    <p>Nova Musica</p>
    <input placeholder='Nome' v-model='name'>
    <input placeholder='Artista' v-model='artist'>
    <input placeholder='Ano Lançamento' v-model='year'>
    <button type="submit" name="Enviar" @click='sendMusic'>Enviar</button>
  </div>
</template>

<script>
import { Music } from '../models/Music'

export default {
  name: 'inputMusic',
  data () {
    return {
      name: '',
      artist: '',
      year: ''
    }
  },
  methods: {
    sendMusic () {
      let music = new Music()
      music.name = this.name
      music.artist = this.artist
      music.year = this.year
      this.$emit('newMusic', music)
      this.clearInputs()
    },
    clearInputs () {
      this.name = ''
      this.artist = ''
      this.year = ''
    }
  }
}
</script>

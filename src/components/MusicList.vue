<template>
  <table>
    <tr>
      <td>Name</td>
      <td>Artist</td>
      <td>Year</td>
      <td>Remove</td>
    </tr>
    <tr v-for='(music, index) in list'>
      <td>{{ music.name }}</td>
      <td>{{ music.artist }}</td>
      <td>{{ music.year }}</td>
      <td><input type="checkbox" name="removeMusic" value="remover" @click="removeMusic(index)"></td>
    </tr>
  </table>
</template>
<style >
  table {
    width: 50%;
    padding-top: 1%;
    margin: auto;
  }
</style>
<script>
  export default {
    props: ['list'],
    data () {
      return {}
    },
    methods: {
      removeMusic (index) {
        this.$emit('removeMusic', index)
      }
    }
  }
</script>

<template>
  <div id="app">
    <div id="board">
      <List  v-for="list in lists" :key="list.id" :list="list"/>
    </div>
    <ModalListItem/>
  </div>
</template>

<script>
import List from './components/List'
import ModalListItem from './components/ModalListItem'

export default {
  name: 'app',
  data () {
    return {
      lists: [
        {
          'id': 1,
          'title': 'Проект 1'
        },
        {
          'id': 2,
          'title': 'Проект 2'
        }
      ]
    }
  },
  components: {
    ModalListItem,
    List
  },
  methods: {}

}

</script>

<style>
  #app {
    font-family: 'Avenir', Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    color: #2c3e50;
  }

  #board {
    padding: 20px;
  }
</style>

<template>
  <div id="app">
    <h1>{{ title }}</h1>
    <add-item v-on:add-list-item="addItem"></add-item>
    <item-list :items="this.items" v-on:delete-item="deleteItem"></item-list>
    <list-title v-on:title-change="changeTitle"></list-title>
  </div>
</template>

<script>
import AddItem from './components/AddItem.vue'
import ItemList from './components/ItemList.vue'
import ListTitle from './components/ListTitle.vue'

export default {
  name: 'app',
  components: {
    'add-item': AddItem,
    'item-list': ItemList,
    'list-title': ListTitle
  },
  data: function() {
    return {
      title: 'My VueJS Todo List',
      items: []
    }
  },
  methods: {
    addItem(item){
      this.items.push(item)
    },
    deleteItem(uuid){
      this.items.splice(this.items.findIndex(item => item.uuid === uuid), 1)
    },
    changeTitle(text){
      this.title = text
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

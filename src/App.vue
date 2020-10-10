<template>
  <div id="app" class="bg-gray-200 w-full h-screen flex flex-col items-center p-4">
    <div>
      <input type="text" placeholder="Add an item" v-model="item" />
      <button @click.prevent="addItem">Add</button>

      <list :items="items" v-on:remove-item="removeItem"></list>
    </div>
  </div>
</template>

<script>
import List from './components/List.vue'

export default {
  name: 'App',
  components: {
    List
  },
  data: function() {
    return {
      item: '',
      items: ['item1', 'item2']
    }
  },

  methods: {
    addItem: function () {
      this.items.push(this.item);
      // this.items.unshift(this.item);
      this.item = '';
    },
    removeItem: function (itemKey) {
      this.items.splice(itemKey, 1);
    }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>

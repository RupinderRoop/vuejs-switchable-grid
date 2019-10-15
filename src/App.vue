<template>
  <div id="app">
    <div class="container">
      <div class="row">
        <div class="col-md-12 text-right">
          <div class="mb-2">
            <button class="icon-style mr-2" @click="selectedView = 'list'">
              <i class="far fa-2x fa-list-alt"></i>
            </button>
            <button class="icon-style" @click="selectedView = 'grid'">
              <i class="fas fa-2x fa-th-large"></i>
            </button>
          </div>
        </div>
      </div>
      <app-list-view :data='data' v-if="selectedView === 'list'"></app-list-view>
      <app-grid-view :data='data' v-if="selectedView === 'grid'"></app-grid-view>
    </div>
  </div>
</template>

<script>
import axios from 'axios'
import ListView from './components/ListView.vue'
import GrifView from './components/GridView.vue'

export default {
  name: 'app',
  data () {
    return {
      data: [],
      selectedView: 'list'
    }
  },
  created () {
    axios.get('https://jsonplaceholder.typicode.com/photos').then(res => {
      const resData = res.data.slice(0, 25)
      this.data = resData
    })
  },
  components: {
    appListView: ListView,
    appGridView: GrifView
  }
}
</script>

<style lang="scss">
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
.icon-style {
  padding: 5px;
  cursor: pointer;
  border-radius: 8px;
}
.icon-style:hover {
  background-color: lightgray;
}
.icon-style:focus {
  outline: none;
}
</style>

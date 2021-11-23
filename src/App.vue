<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png">
    <!-- <HelloWorld msg="Welcome to Your Vue.js App"/> -->
    <header class="change_store">
    <h1 class="change_resource">Store Resource Change</h1>
    </header>
    <button
      v-for="tab in tabs"
      :key="tab"
      @click="selected = tab;"
      :class="['tab-btn', { active: selected === tab }]"
    >
      {{ tab }}
    </button>
    <component :is="selected" class="tab"></component>
    
    </div>
</template>

<script>
// import HelloWorld from './components/HelloWorld.vue'
import StoredResource from './components/StoredResource.vue'
import AddResource from './components/AddResource.vue'

export default {
  name: 'App',
  components: {
    // HelloWorld,
    StoredResource,
    AddResource
  },
  data: function() {
    return{
      tabs: ["StoredResource", "AddResource"],
      selected: "StoredResource",
      
    }
  },
  methods: {
    
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
.change_store{
  width: 100%;
  height: 70px;
  background-color: #640032;
  display: flex;
  justify-content: center;
  align-items: center;
}
.change_resource{
  color: #fff;
}
.tab-btn {
  padding: 15px 25px;
  background-color: #fff;
  cursor: pointer;
  margin-bottom: 1rem;
  border: 2px solid #cccccc;
  outline: none;
  margin-top: 40px;
}

.active {
  border-bottom: 3px solid green;
  
  background-color: #640032;
}

.tab {
  border: 1px solid #ccc;
  padding: 10px;
}
</style>

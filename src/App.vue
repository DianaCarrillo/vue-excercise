<template>
  <div id="app">
    <Title msg="My To-Do List"/>
    <p>Write down things you have to do</p>
    <InputToDo/>
    <!-- <ToDoList/> -->
  </div>


</template>

<script>
import Title from './components/Title.vue'
import InputToDo from './components/InputToDo.vue'
// import ToDoList from './components/ToDoList.vue'

export default {
  name: 'app',
  components: {
    Title,
    InputToDo
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: black;
  margin-top: 60px;
}
</style>

<template>
  <h1>To-do list</h1>
  <div class="to-do-list">
    <h2>Add task</h2>
    <Input @addTask="appendTask"/>
    <h2>tasks</h2>
    <Todos @removeTask="removeTask" :tasks="tasks"/>
  </div>
</template>

<script>
import Todos from './components/Todos.vue'
import Input from './components/Input.vue'

export default {
  name: 'App',
  components: {
    Todos,
    Input
  },
  data(){
    return{
      tasks: ['wash clothes', 'wash utensils', 'go for shopping']
    }
  },
  methods: {
    appendTask(task){
      this.tasks=[...this.tasks, task];
    },
    removeTask(task){
      this.tasks=this.tasks.filter(item=>{
        return item!==task;
      })
    }
  }
}
</script>

<style>
*{
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
h1{
  margin: 0 auto 1em;
}
h2{
  margin: .5em;
  text-align: left;
}
.to-do-list{
  display: flex;
  flex-direction: column;
  padding: 2em;
  width: 450px;
  margin: 0 auto;
  border: none;
  border-radius: 3px;
  box-shadow: 1px 1px 30px 1px rgb(243, 243, 243);
}
button{
  padding: .5em 1em;
  border: none;
  outline: none;
  background-color: teal;
}
@media only screen and (max-width: 768px){
  .to-do-list{
  margin: 1em auto;
  padding: 1.5em;
  width: 94vw;
}
}
</style>

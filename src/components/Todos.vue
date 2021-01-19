<template>
<div class="to-dos">
    <div v-for="task in tasks" :key="task" class="to-do">
      <div class="task">
        <input @click="clearTask(task)" type="checkbox">
        <p class="task-description">{{task}}</p>
      </div>
      <button @click="removeTask(task)" class="remove">remove</button>
    </div>
</div>
</template>

<script>
export default {
    name: 'Todos',
    props: ['tasks'],
    data(){
        return{
        
        }
    },
    methods: {
        removeTask(task){
            this.$emit('removeTask', task);
        },
        clearTask(task){
            let clearedTask;
            let tasks=document.querySelectorAll('.task-description');
            for(let i=0; i<tasks.length; i++){
                if(tasks[i].innerText===task){
                   clearedTask=tasks[i] 
                }
            }
            clearedTask.classList.toggle('cleared');
        }
    }
}
</script>

<style>
.to-dos{
    display: flex;
    flex-direction: column;
    width: 100%;
}
.to-do{
    display: flex;
    flex-direction: row;
    justify-content: space-between;
    align-items: center;
    padding: .5em 0;
    width: 100%;
    border-bottom: 1px solid aqua;
}
.task{
    display: flex;
    flex-direction: row;
    align-items: center;
}
.cleared{
    text-decoration: line-through;
}
input[type="checkbox"]{
    margin: 0 1em;
}
</style>
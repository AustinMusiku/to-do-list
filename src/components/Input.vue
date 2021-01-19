<template>
  <form @submit="addTask" class="input-bar">
      <input type="text" ref="inputTask" placeholder="Enter task (E.g., wash clothes, clean room)">
      <button type="submit" class="addTask">Add task</button>
  </form>
</template>

<script>
export default {
    name: 'input',
    data(){
        return{

        }
    },
    methods: {
        addTask(e){
            e.preventDefault();
            this.$emit('addTask', this.$refs.inputTask.value);
            this.$refs.inputTask.value='';
        }
    }
}
</script>

<style scoped>
.input-bar{
    position: relative;
    display: flex;
    flex-direction: row;
    justify-content: space-between;
    margin-bottom: 1em;
}
input{
    padding: .75em 1em;
    border: 1px solid rgba(51, 51, 51, 0.178);
    outline: none;
    width: 80%;
}
</style>
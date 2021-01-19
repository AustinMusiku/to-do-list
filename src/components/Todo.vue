<template>
  <div class="to-do">
      <input type="checkbox">
      <p>{{task}}</p>
      <button class="remove">remove</button>
  </div>
</template>

<script>
export default {
    name: 'Todo',
    data(){
        return{
            task:['wash clothes']
        }
    },
    methods: {
        
    }
}
</script>

<style>
.to-do{
    display: flex;
    flex-direction: row;
    width: 100%;
}
</style>
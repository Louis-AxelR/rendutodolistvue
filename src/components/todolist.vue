<template>
    <div id="taches">
<div id="tache">
    <ul v-for="(task, index) in tasks" :key="(task, index)">
        <li>

            <input @click="check(index)" type="checkbox">
            <p v-bind:class="{'checked' : task.checked }">{{ task.name }}</p>
            <div @click="remover(index)" id="poubelle"><i class="fas fa-trash"></i></div>
        </li>
    </ul>
   
</div>
    </div>
</template>


<script>
export default {
  name: 'todolist' ,
  props:['tasks'] ,
  methods :{
      check(index){
          this.$emit("checked", index)
      },
      remover(index){
          this.$emit("delete", index)
      },

      
  }

}

</script>

<style scoped>
ul li{
    display: flex;
    flex-direction: row;
    justify-content: space-between;
    padding:20px;
}

.checked{
    color: red;
    text-decoration: line-through;
}
i{
    color:red;
}
</style>
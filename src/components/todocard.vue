<script>

import newtodo from '../components/newtodo.vue';
import todolist from '../components/todolist.vue';

export default {
    name: 'todocard',
    data(){
        return{
      title: ' Vuejs Tutorial TodoList '  ,    
    tasks : [],
   

        }
        
    },
components: {
    newtodo,
    todolist
  },

    computed: {
        jour: function(){
    var date = new Date();
    var days = ["Dimanche", "Lundi", "Mardi", "Mercredi", "Jeudi", "Vendredi", "Samedi"]
    var months = [ "Janvier", "Février", "Mars", "Avril", "Mai", "Juin", "Juillet", "Aout", "Septembre", "Octobre", "Novembre", "Décembre"
    ]

    var DayNumber = date.getDate()
    var ActualDay = days[date.getDay()]
    var ActualMonth = months[date.getMonth()]

    return  ActualDay + " " + DayNumber + " " + ActualMonth
    
        }
    },

    methods:{
    addTask(task){
        var newTask = {
            name: task,
            ckecked: false
        }
        this.tasks.push(newTask)
        console.log(this.tasks)
        
    },
    checkTask(index){
        this.tasks[index].checked = !this.tasks[index].checked
    },
    removeTask(index){
        this.tasks.splice(index, 1)
    },
    deleteall(){
        this.tasks.splice(0)
    }


    },
}
</script>




<template>
<div id="app">
<div class="card">
        <div class="card-header">
            <h1>{{ jour }}</h1>
            <p id="centre">{{ title }}</p>
            <p v-if="tasks.length > 1">{{ tasks.length }} taches</p>
            <p v-else> {{ tasks.length }} tache</p>
        </div>
        <div class="card-content">
            
<newtodo @newTask='addTask'/>
<button @click="deleteall" class="button is-medium is-fullwidth button is-danger is-light">tout supprimer</button>
<todolist  v-bind:tasks="tasks" @checked="checkTask" @delete="removeTask"  />
        </div>

    </div>
</div>
    





</template>







<style scoped>
.card-header{
    padding: 20px;
    display: flex;
    flex-direction: row;
    justify-content: space-between;
    font-weight: 500;
    font-size: 20px;
}

.card-header #centre{
    color: #1CD6BA;
    
}
button{
    margin-top: 20px;
}

</style>
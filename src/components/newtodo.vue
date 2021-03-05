<template>
    <div id="app">
<label for="ajouter"></label>
<input placeholder="ajouter votre tache ..." v-model="taskName" name="Ajouter">
<button v-on:click=sendTask><i class="fas fa-plus-circle"></i></button>
    </div>
</template>

<script>
export default {
    name: 'newtodo',
    data () {
        return{
            taskName: ""
        }
    },

    methods: {
        sendTask() {
            this.$emit('newTask', this.taskName)
        }

    }
    
}
</script>

<style scoped>
button{
   border: none;
   background-color: white;
}
input{
    border: white;
    border-bottom: 3px solid #48C774;
    margin-right: 30px;
    width: 200px;
    
}

i{
    
    color:#48C774;
     font-size: 50px;
    

}
input::placeholder{
    color: #D9D9D9;
    font-size: 18px;
}
</style>
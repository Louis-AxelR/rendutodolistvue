<template>
    <div id="app">
<label for="ajouter"></label>
<input placeholder="ajouter votre tache ..." v-model="taskName" name="Ajouter">
<button v-on:click=sendTask><span>+</span></button>
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
    border-radius: 50%;
    height: 50px;
     width: 50px;
     background-color: #48C774;
     border: none;
}
input{
    border: white;
    border-bottom: 3px solid #48C774;
    margin-right: 30px;
    width: 200px;
    
}
button span{
    font-size: 20px;
    color:white;
    
}
input::placeholder{
    color: #D9D9D9;
    font-size: 18px;
}
</style>
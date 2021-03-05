
<template>
  <div id="app">
     <section class="hero is-warning is-bold is-fullheight">
      <div class="hero-body">
        <div class="container has-text-centered">
        
          <todocard/>
        </div>
      </div>

      <div class="hero-foot">
        <div class="container">
          
          <div class="content has-text-centered pb-5">
            <p>
              <strong>Atelier Mars 2021</strong>
            </p>
            <p>
              Découvrez comment styliser simplement votre ToDo list avec 
              <a class="has-text-primary" href="https://bulma.io/">
                <strong></strong>
              </a> 
            </p>
          </div>
        </div>
      </div>
    </section>
  </div>
</template>

<script>

import todocard from './components/todocard.vue';

export default {
  name: 'app',
  components: {
    todocard
  },
  data () {
    return {
      msg: 'Hello, et bienvenue sur la demo TodoList en Vue.js!'
    }
  }
}
</script>

<style>
</style>
<template>
  <v-app>

  <h1>Desafío Formulario Vue-Cli Merzario</h1>
   
    <Form/>
  </v-app>
</template>

<script>
import Form from './components/Form.vue'
//import HelloWorld from './components/HelloWorld';

export default {
  name: 'App',

  components: {
      Form,
  }, 
    data: () => ({
      
    }),

    methods: {
     
    },
  }
</script>

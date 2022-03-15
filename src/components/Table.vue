<template>
  <v-row justify="center">
    <v-dialog
      v-model="dialog"
      persistent
      max-width="450"
    >
      <template v-slot:activator="{ on, attrs }">

        <v-list-item link
          v-bind="attrs"
          v-on="on"
        >
            <v-list-item-title>Enviar</v-list-item-title>
           </v-list-item>
      </template>
 
      <!-- <v-card>
           <v-card-title class="text-h5">
             {{nombre}}
          </v-card-title>

          <v-card-title class="text-h5">
              {{apellido}}
          </v-card-title>
      
           <v-card-text-title>
              {{email}}
           </v-card-text-title>

            <v-card-text-title>
              {{telefono}}
           </v-card-text-title>

            >
           <v-card-actions>
          <v-spacer></v-spacer>
           <v-btn
            color="green darken-1"
            text
            @click="dialog = false"
          > 
            Aceptar
          </v-btn>
        
        </v-card-actions>
      </v-card> -->

<table class="table table-white">
  <thead>
    <tr>
      <th scope="col">Nombre</th>
      <th scope="col">Apellido</th>
      <th scope="col">Email</th>
      <th scope="col">Tel</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>{{nombre}}</td>
      <td>{{apellido}}</td>
      <td>{{email}}</td>
      <td>{{telefono}}</td>
    </tr>
 
  </tbody>
 
    <button type="button" class="btn bg-success"   
    text
    @click="dialog = false"
    > 
    Aceptar
    </button>
</table>

    </v-dialog>
    </v-row>
</template>
<script>

 export default {
      name: 'Table',
      Components:{
     
      },
   props: ['nombre','apellido','telefono','email'],

      data () {
        return {
              dialog: false,
        }
    },
 
  }
</script>


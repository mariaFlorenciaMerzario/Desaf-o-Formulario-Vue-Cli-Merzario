<template>
  <v-form
    ref="form"
    v-model="valid"
    lazy-validation
    class="w-75"
  >
    <v-text-field
      v-model="name"
      :counter="10"
      :rules="nameRules"
      label="Nombre"
      required
    ></v-text-field>

      <v-text-field
      v-model="apellido"
      :counter="10"
      :rules="nameRules"
      label="Apellido"
      required
    ></v-text-field>

    <v-text-field
      v-model="email"
      :rules="emailRules"
      label="E-mail"
      required
    ></v-text-field>

      <v-text-field
      v-model="telefono"
      :rules="telRules"
      label="Mobil"
      aria-placeholder="Ingrese el número sin el 15"
      required
    ></v-text-field>

   
    <v-btn
      :disabled="!valid"
      color="primary"
      class="mr-4"
      @click="validate"
    >
      Validar
    </v-btn>

    <v-btn
      color="error"
      class="mr-4"
      @click="reset"
    >
      Resetear 
    </v-btn>

    <!-- aca empieza la modal -->
    <template>
    <div data-app class="m-2">
        <v-row justify="center">
        <v-dialog
        v-model="dialog"
        persistent
        max-width="290"
        >
        <template v-slot:activator="{ on, attrs }">
            <v-btn
            color="primary"
            dark
            v-bind="attrs"
            v-on="on"
            >
            <Table
                :nombre='name'
                :apellido='apellido'
                :email='email'
                :telefono='telefono'
            />
            </v-btn>
        </template>
        </v-dialog>
    </v-row> 
    </div>          
    </template>

  </v-form>
</template>

<script>
import Table from './Table.vue'
  export default {
  components: { Table },
    data: () => ({
      dialog:false,
      valid: true,
      name: '',
      nameRules: [
        v => !!v || 'El campo es requerido',
        v => (v && v.length <= 10) || 'El nombre no debe tener mas de 10 caracteres',
      ],
      email: '',
      emailRules: [
        v => !!v || 'El E-mail es requerido',
        v => /.+@.+\..+/.test(v) || 'El e-mail debe ser válido',
      ],
      telefono:'',
      apellido:'',

      telRules: [
        v => !!v || 'El teléfono movil es requerido',
        v => (v && v.length <= 10) || 'El nombre no debe tener mas de 10 caracteres',
      ],
     
    }),

    methods: {
      validate () {
        this.$refs.form.validate()
      },
      reset () {
        this.$refs.form.reset()
      },

    },
  }
</script>
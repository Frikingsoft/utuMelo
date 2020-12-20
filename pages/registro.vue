<template>
    <form>
         <v-text-field
      v-model="name"
      :error-messages="nameErrors"
      :counter="10"
      label="Name"
      required
      @input="$v.name.$touch()"
      @blur="$v.name.$touch()"
    ></v-text-field>
     <v-btn
      class="mr-4"
      @click="submit"
    >
      submit
    </v-btn>
    </form> 
</template>
<script>
import { validationMixin } from 'vuelidate'
import { required, maxLength, email } from 'vuelidate/lib/validators'
export default {
    mixins: [validationMixin],
    validations: {
      name: { required, maxLength: maxLength(10) },
    },
    data(){
        return{
            name: '',
        }
    }
}
</script>

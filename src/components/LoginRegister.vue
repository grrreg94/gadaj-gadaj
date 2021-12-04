<template>
  <q-form @submit="submitForm">
    <q-input 
    v-if="tab == 'rejestracja'"
    class="q-mb-md"
    outlined 
    v-model="formData.name" 
    label="Name" />
    <q-input 
    class="q-mb-md"
    outlined 
    v-model="formData.email" 
    type="email"
    label="Email" />
    <q-input 
    class="q-mb-md"
    outlined
    type="password"
    v-model="formData.password" 
    label="Hasło" />
    <q-btn 
    type="submit"
    color="primary"
    :label="tab" />
  </q-form>
</template>

<script>
export default {
  props: ['tab'],
  data(){
  return{
      formData: {
        name: '',
        email: '',
        password: ''
      }
   }
 },
 methods:{
   submitForm(){
    // if(this.tab == 'login')
    // else

   }
 }
}

</script>

<style>

</style>
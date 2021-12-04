<template>
  <q-page class="flex q-pa-md">
    <q-card class="full-width">
      <q-tabs
        v-model="tab"
        dense
        class="text-grey"
        active-color="primary"
        indicator-color="primary"
        align="justify"
        narrow-indicator
      >
        <q-tab name="login" label="Login" />
        <q-tab name="rejestracja" label="Rejestracja" />
      </q-tabs>

      <q-separator />

      <q-tab-panels v-model="tab" animated>
        <q-tab-panel name="login">
        <login-register :tab="tab" />
        </q-tab-panel>

        <q-tab-panel name="rejestracja">
         <login-register :tab="tab" />
        </q-tab-panel>
        
      </q-tab-panels>
    </q-card>
  </q-page>
</template>

<script>
import { ref } from "vue";
import LoginRegister from 'components/LoginRegister.vue';

export default {
  setup() {
    return {
      tab: ref("login"),
    };
  },

  components:{
    'login-register' : require('components/LoginRegister.vue').default
  }
};
</script>

    LoginRegister
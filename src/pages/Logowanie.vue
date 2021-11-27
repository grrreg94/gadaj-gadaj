<template>
  <q-page class="flex q-pa-md ">
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
          <q-tab name="login" label="Zaloguj" />
          <q-tab name="register" label="Zarejestruj" />
        </q-tabs>

        <q-separator />

        <q-tab-panels v-model="tab" animated>
          <q-tab-panel name="login">
<loguj-rejestruj></loguj-rejestruj>
          </q-tab-panel>

          <q-tab-panel name="register">

            <h5>Zarejestruj</h5>
          </q-tab-panel>
          
        </q-tab-panels>
      </q-card>
  </q-page>
</template>

<script>
import { defineComponent } from 'vue';

import { ref } from 'vue'

export default {
  setup () {
    return {
      tab: 'login'
    }
    coponents: {
      'login-rejestruj' ; require("components/logReg.vue").default
    }
  }
}
</script>

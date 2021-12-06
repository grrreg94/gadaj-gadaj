<template>
  <q-page class="flex column">
    
    <div class="q-pa-md column col justify-end">
      <q-chat-message
        v-for="message in messages"
        :key="message.text"
        :name="message.from"
        :text="[message.text]"
        :sent="message.from == 'ja' ? true : false"
      />
    </div>
    <q-footer elevated class="q-pa-sm">
      <q-toolbar>
        <q-form @submit="sendMessage" class="full-width">
          <q-input
            v-model="newMessage"
            @keyup.enter="sendMessage"
            bg-color="white"
            label="Wiadomosc"
            dense
            >

            <template v-slot:after>
              <q-btn 
               @click="sendMessage"
               type="submit"
               round
               dense 
               color="lime-11"
               flat 
               icon="send"
              />
            </template>
          </q-input>
        </q-form>
      </q-toolbar>
    </q-footer>
  </q-page>
</template>

<script>
import { defineComponent } from "vue";

export default defineComponent({
  data() {
    return {
      newMessage: '',
      messages: [
        {
          text: "Hej",
          from: "ja",
        },
        {
          text: "Spierdaaj",
          from: "ktos",
        },
        {
          text: "Dobra",
          from: "ja",
        },
      ],
    };
  },

  methods: {
    sendMessage() {
      this.messages.push({
        text: this.newMessage,
        from: 'ja'
      })
      this.newMessage = ''
    }
  }
});


</script>

<template>
  <q-page class="flex column">
    
    <div class="q-pa-md column col justify-end">
      <q-chat-message
        v-for="message in messages"
        :key="message.key"
        :name="message.key"
        :text="[message.value]"
        :sent="message.key == 'ja' ? true : false"
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
        // {
        //   text: "Hej",
        //   from: "ja",
        // },
        // {
        //   text: "Spierdaaj",
        //   from: "ktos",
        // },
        // {
        //   text: "Dobra",
        //   from: "ja",
        // },
      ],
    };
  },

  methods: {
    sendMessage() {
      var dict = new Dictionary();
      dict.add("ja",this.newMessage);
      // this.messages.push({
      //   text: this.newMessage,
      //   from: 'ja'
      // })
      this.newMessage = ''
      console.log(dict.values());
      console.log(dict.keys());
      console.log(dict.size());
    }
  }
});

function Dictionary(){
  this.data = {};
  this.add = function(key, value){
    this.data[key] = value;
  };
  this.remove = function(key) {
    delete this.data[key];
  };
  this.has = function(key){
    return key in this.data;
  };
  this.get = function(key) {
    return this.has(key) ? this.data[key] : undefined;
  };
  this.clear = function() {
    for (var key in this.data) {
      delete this.data[key];
    }
  };
  this.size = function() {
    var n = 0;
    for (var key in this.data) {
      n++;
    }
    return n;
  };
  this.keys = function() {
    var keys = [];
    for (var key in this.data) {
      keys.push(key);
    }
    return keys;
  };
  this.values = function(){
    var values = [];
    for (var key in this.data) {
      if (this.has(key)) {
        values.push(this.data[key]);
      }
    }
    return values;
  };
  this.viewAll = function() {
    for (var key in this.data) {
      console.log(key + " -> " + this.data[key]);
    }
  };
}

</script>

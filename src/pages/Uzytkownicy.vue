<template>
  <q-page class="flex q-pa-md">
    <q-list separator class="full-width" >
      <q-item
        v-for="contact in contacts"
        :key="contact.id"
        class="q-my-sm"
        to="/chat"
        clickable
        v-ripple
      >
        <q-item-section avatar>
          <q-avatar color="primary" text-color="white">
            {{ contact.name.charAt(0) }}
          </q-avatar>
        </q-item-section>

        <q-item-section>
          <q-item-label>{{ contact.name }}</q-item-label>
        </q-item-section>

        <q-item-section side>
          <q-icon name="chat_bubble" v-if="contact.online" color="green   -14" />
          <q-icon
            class="grey_chat_bubble"
            name="chat_bubble"
            v-else
            color="primary"
          />
        </q-item-section>
      </q-item>
    </q-list>
  </q-page>
</template>

<script>
export default {
  data() {
    return {
      contacts: [
        {
          id: 1,
          name: "Ruddy Jedrzej",
          online: true,
        },
        {
          id: 2,
          name: "Mallorie Alessandrini",
          online: false,
        },
        {
          id: 3,
          name: "Elisabetta Wicklen",
          online: true,
        },
      ],
    };
  },
};
</script>


<style lang="scss">
.grey_chat_bubble {
  filter: grayscale(40%);
  opacity: 50%,

}
</style>
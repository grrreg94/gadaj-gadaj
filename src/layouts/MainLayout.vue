<template>
  <q-layout view="lHh Lpr lFf">
    <q-header elevated class="header"> 
       <q-img 
         src="../statics/fiber.jpg"
         class="header-image absolute-top"/>
          <q-btn
          class="absolute-right "
          to="/logowanie"
          icon="account_circle"
          flatdense
          flat
          label="Login"
          />

      <q-toolbar>        
        <q-toolbar-title class="absolute-center q-px-lg q-pt-xl q-mb-md">
          <h3 class="gadaj_gadaj">{{title}}</h3>
        </q-toolbar-title>
      </q-toolbar>
      
    </q-header>
    <q-page-container>
      <router-view />
     </q-page-container>
  </q-layout>
</template>

<script>
import EssentialLink from 'components/EssentialLink.vue'

const linksList = [
  {
    title: 'Docs',
    caption: 'quasar.dev',
    icon: 'school',
    link: 'https://quasar.dev'
  },
  {
    title: 'Github',
    caption: 'github.com/quasarframework',
    icon: 'code',
    link: 'https://github.com/quasarframework'
  },
  {
    title: 'Discord Chat Channel',
    caption: 'chat.quasar.dev',
    icon: 'chat',
    link: 'https://chat.quasar.dev'
  },
  {
    title: 'Forum',
    caption: 'forum.quasar.dev',
    icon: 'record_voice_over',
    link: 'https://forum.quasar.dev'
  },
  {
    title: 'Twitter',
    caption: '@quasarframework',
    icon: 'rss_feed',
    link: 'https://twitter.quasar.dev'
  },
  {
    title: 'Facebook',
    caption: '@QuasarFramework',
    icon: 'public',
    link: 'https://facebook.quasar.dev'
  },
  {
    title: 'Quasar Awesome',
    caption: 'Community Quasar projects',
    icon: 'favorite',
    link: 'https://awesome.quasar.dev'
  }
];

import { defineComponent, ref } from 'vue'

export default defineComponent({
 computed: {
   title() {
     let currentPath = this.$route.fullPath
     if (currentPath == '/') return 'Gadaj-Gadaj' 
     else if (currentPath == '/logowanie') return 'Logowanie' 
     else if (currentPath == '/chat') return 'no już, Gadaj-Gadaj'
   }
 }

 
 
})
</script>

<style lang="scss">
.header{
  height: 11%
}
  .header-image{
    height: 100%;
    z-index: -1;
    opacity: 0.4;
    filter: grayscale(0%)
  }

.gadaj_gadaj {
    font-family:'Franklin Gothic Medium', 'Arial Narrow', Arial, sans-serif;
    font-size: 3rem;
    letter-spacing: .5rem;
    color: rgb(239, 255, 97);
    text-shadow: 2px 2px 0 #0627e3;
    padding-left: 1rem;
}

  </style>
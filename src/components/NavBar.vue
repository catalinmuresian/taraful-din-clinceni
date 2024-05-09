<template>
  <div class="nav-bar">
   <div class="main-container">
     <q-toolbar class="bg-teal-5 text-white shadow-2">
      <q-img
        style="max-width: 40px;"
        src="~assets/quasar-logo-vertical.svg"></q-img>
       <q-space />
       <q-btn-toggle
         v-model="tab"
         flat
         @click="handleNavigate(tab)"
         stretch
         toggle-color="yellow"
         :options="navLinks"
       />
     </q-toolbar>
   </div>
  </div>
</template>

<script setup>

import {ref} from "vue";
import {useRouter} from "vue-router";
const tab = ref('')
const router = useRouter()

const navLinks = ref([
  {
    label: 'Acasa',
    value: '/'
  },
  {
    label: 'Despre noi',
    value: '/despre_noi'
  },
  {
    label: 'Contact',
    value: '/contact'
  },
])

function handleNavigate (route) {
  router.push(route)
}
</script>

<style lang="scss">
.nav-bar {
  .main-container {
    display: flex;
    justify-content: center;
    ul {
      display: flex;
      gap: 20px;
      li {
        font-size: 14px;
        list-style-type: none;
      }
    }
  }
}

</style>

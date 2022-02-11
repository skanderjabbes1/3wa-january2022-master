<template>
  <div>
    <ul class="nav nav-tabs">
      <li class="nav-item" v-for="(tab, i) in tabs" :key="i" @click="currentTab=tab">
        <a class="nav-link" :class="{ active: tab === currentTab }">{{ tab }}</a>
      </li>
    </ul>
    <component :is="currentTab" class="tab p-3"></component>
  </div>
</template>

<script>
// @ is an alias to /src
import ContactList from '@/components/ContactList.vue'
import AddContact from '@/components/AddContact.vue'
export default {
  name: 'Home',
  components: {
    ContactList,
    AddContact
  },
  data() {
    return {
      currentTab: "ContactList",
      tabs: ['ContactList', 'AddContact']
    }
  }
}
</script>

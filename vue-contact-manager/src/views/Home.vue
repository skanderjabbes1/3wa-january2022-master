<template>
  <div>
    <ul class="nav nav-tabs">
      <li class="nav-item" v-for="(tab, i) in tabs" :key="i" @click="currentTab=tab">
        <a class="nav-link" :class="{ active: tab === currentTab }">{{ tab }}</a>
      </li>
    </ul>
    <component
      :is="currentTab"
      :list="contactList"
      @add-contact="addContact"
      @delete-contact="deleteContact"
      class="tab p-3"
      ></component>
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
      tabs: ['ContactList', 'AddContact'],
       contactList: [
        {
          id: 1,
          name: "Leanne Graham",
          email: "leanne.graham@gmail.com",
          phone: "+21622334455",
          address: {
            street: "Kulas Light",
            city: "Gwenborough",
          },
        },
        {
          id: 2,
          name: "Ervin Howell",
          email: "Shanna@melissa.tv",
          phone: "010-692-6593 x09125",
          address: {
            street: "Victor Plains",
            city: "Wisokyburgh",
          },
        },
        {
          id: 3,
          name: "Clementine Bauch",
          email: "Nathan@yesenia.net",
          phone: "1-463-123-4447",
          address: {
            street: "Douglas Extension",
            city: "McKenziehaven",
          },
        },
      ],
    }
  },
  methods: {
    addContact(contact) {
      this.contactList.push(contact);
      this.currentTab = "ContactList";
    },
    deleteContact(contact) {
      this.contactList = this.contactList.filter(c => c.id !== contact.id);
    }
  },
}
</script>

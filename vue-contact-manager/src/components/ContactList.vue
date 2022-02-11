<template>
  <div>
    <h1>Contact List</h1>
    <div class="row">
      <div class="col">
        <ul class="list-group">
          <li
            v-for="contact in list"
            v-bind:key="contact.id"
            class="list-group-item"
            @click="currentContact = contact"
          > {{ contact.name }}
          </li>
      </ul>
      </div>
      <div class="col">
        <ContactDetails v-if="currentContact" :contact="currentContact"></ContactDetails>
      </div>
    </div>
  </div>
</template>

<script>
import ContactDetails from './ContactDetails.vue';
export default {
    name: 'ContactList',
    components: {
      ContactDetails,
    },
    data() {
      return {
        currentContact: null,
        list: [
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
}
</script>

<style>

</style>
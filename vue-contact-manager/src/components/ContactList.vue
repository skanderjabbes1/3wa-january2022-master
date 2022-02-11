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
        <ContactDetails
          v-if="currentContact"
          :contact="currentContact"
          @delete-contact="deleteContact"
          ></ContactDetails>
      </div>
    </div>
  </div>
</template>

<script>
import ContactDetails from './ContactDetails.vue';
export default {
    name: 'ContactList',
    props: {
        list: Array
    },
    components: {
      ContactDetails,
    },
    data() {
      return {
        currentContact: null,
      }
    },
    methods: {
      deleteContact() {
        this.$emit('delete-contact', this.currentContact);
        this.currentContact = null;
      }
    },
}
</script>

<style>

</style>
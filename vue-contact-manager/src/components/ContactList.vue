<template>
  <div>
    <h1><fa-icon icon="address-book"></fa-icon> Contact List</h1>
    <ul class="list-group">
      <li
        v-for="contact in list"
        v-bind:key="contact.id"
        class="list-group-item"
      > {{ contact.name }}
      </li>
    </ul>
  </div>
</template>

<script>
export default {
    name: 'ContactList',
    props: {
        list: Array
        },
}
</script>

<style>

</style>
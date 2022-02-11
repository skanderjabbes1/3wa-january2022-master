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
          > {{ contact.name }}
          </li>
      </ul>
      </div>
      <div class="col"></div>
    </div>
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
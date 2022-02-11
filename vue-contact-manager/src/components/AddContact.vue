<template>
  <form @submit.prevent="submitForm">
        <div class="mb-3">
            <label for="contactName" class="form-label">Name</label>
            <input v-model="contact.name" type="text" class="form-control" id="contactName">
        </div>
        <div class="row mb-3">
            <div class="col">
                <label for="contactEmail" class="form-label">Email address</label>
                <input v-model="contact.email" type="email" class="form-control" id="contactEmail">
            </div>
            <div class="col">
                <label for="contactPhone" class="form-label">Phone number</label>
                <input v-model="contact.phone" type="text" class="form-control" id="contactPhone">
            </div>
        </div>
        <div class="row mb-3">
            <div class="col">
                <label for="contactStreetAddress" class="form-label">Street Address</label>
                <input v-model="contact.address.street" type="text" class="form-control" id="contactStreetAddress">
            </div>
            <div class="col">
                <label for="contactCity" class="form-label">City</label>
                <input v-model="contact.address.city" type="text" class="form-control" id="contactCity">
            </div>
        </div>
        <button type="submit" class="btn btn-primary">Add</button>
    </form>
</template>

<script>
export default {
    data() {
        return {
            contact: {
                name: '',
                email: '',
                phone: '',
                address: {
                    street: '',
                    city: '',
                },
            },
            }
        },
    methods: {
        submitForm() {
            this.$emit('add-contact', this.contact);
            this.contact = {
                name: '',
                email: '',
                phone: '',
                address: {
                    street: '',
                    city: '',
                },
            };
        },
    }
}
</script>

<style>

</style>
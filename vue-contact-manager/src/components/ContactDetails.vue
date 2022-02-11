<template>
    <div class="card" style="width: 28rem;">
        <div class="card-body">
            <h5 class="card-title"> {{ contact.name }}</h5>
        </div>
        <ul class="list-group list-group-flush">
            <li class="list-group-item"> {{ contact.email }}</li>
            <li class="list-group-item"> {{ contact.phone }}</li>
            <li class="list-group-item"> {{ contact.address.street }}</li>
            <li class="list-group-item"> {{ contact.address.city }}</li>
        </ul>
        <div class="card-footer">
            <div class="btn btn-outline-warning" data-bs-toggle="modal" data-bs-target="#editModal">Edit</div>
            <div @click="deleteContact" class="btn btn-outline-danger">Delete</div>
        </div>
        <!-- Modal -->
        <div class="modal fade" id="editModal" tabindex="-1" aria-labelledby="exampleModalLabel" aria-hidden="true">
        <div class="modal-dialog">
            <div class="modal-content">
            <div class="modal-header">
                <h5 class="modal-title" id="exampleModalLabel">Edit contact: <strong>{{ contact.name }}</strong></h5>
                <button type="button" class="btn-close" data-bs-dismiss="modal" aria-label="Close"></button>
            </div>
            <div class="modal-body">
                <form>
                    <div class="mb-3">
                        <label for="contactName" class="form-label">Name</label>
                        <input v-model="editContact.name" type="text" class="form-control" id="contactName">
                    </div>
                    <div class="row mb-3">
                        <div class="col">
                            <label for="contactEmail" class="form-label">Email address</label>
                            <input v-model="editContact.email" type="email" class="form-control" id="contactEmail">
                        </div>
                        <div class="col">
                            <label for="contactPhone" class="form-label">Phone number</label>
                            <input v-model="editContact.phone" type="text" class="form-control" id="contactPhone">
                        </div>
                    </div>
                    <div class="row mb-3">
                        <div class="col">
                            <label for="contactStreetAddress" class="form-label">Street Address</label>
                            <input v-model="editContact.address.street" type="text" class="form-control" id="contactStreetAddress">
                        </div>
                        <div class="col">
                            <label for="contactCity" class="form-label">City</label>
                            <input v-model="editContact.address.city" type="text" class="form-control" id="contactCity">
                        </div>
                    </div>
                </form>
            </div>
            <div class="modal-footer">
                <button type="button" class="btn btn-secondary" data-bs-dismiss="modal">Close</button>
                <button type="button" class="btn btn-primary">Save changes</button>
            </div>
            </div>
        </div>
        </div>
    </div>
</template>

<script>
export default {
    props: ['contact'],
    methods: {
        deleteContact() {
            if(confirm("Delete this contact?")) {
                this.$emit('delete-contact');
            }
        }
    },
    computed: {
        editContact() {
            return this.contact 
        }
    },
}
</script>

<style>

</style>
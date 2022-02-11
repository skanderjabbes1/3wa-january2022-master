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
            <div class="btn btn-outline-warning">Edit</div>
            <div @click="deleteContact" class="btn btn-outline-danger">Delete</div>
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
}
</script>

<style>

</style>
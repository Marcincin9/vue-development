<template>
    <li>
        <h2>{{name}}</h2>
        <button @click="toggleDetails">Show Details</button>
        <ul v-if="detailsAreVisible">
            <li><strong>Phone:</strong>{{phoneNumber}}</li>
            <li><strong>Email:</strong>{{emailAddress}}</li>

        </ul>
        <button @click="$emit('delete', id)">Delete</button>
    </li>
</template>
<script>
export default {
    // props: ['name','phoneNumber','emailAddress'],
    props: {
        id: {
            type: String,
            require: true
        },
        name: {
            type: String,
            require: true
        },
        phoneNumber: {
            type: String,
            require: true
        },
         emailAddress: {
            type: String,
            require: true
        },
    },
    emits:['delete'],
  data(){
      return {
          detailsAreVisible: false,
     };
  },
  methods: {
      toggleDetails(){
          this.detailsAreVisible = !this.detailsAreVisible;
        
        }
    },
};
</script>
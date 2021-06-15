<template>
    <li>
        <h2>{{name}}</h2>
        <button @click="toggleDetails">Show Details</button>
        <ul v-if="detailsAreVisible">
            <li><strong>Phone:</strong>{{phoneNumber}}</li>
            <li><strong>Email:</strong>{{emailAddress}}</li>
        </ul>
    </li>
</template>
<script>
export default {
    props: [
        'name',
        'phoneNumber',
        'emailAddress'
    ],
  data(){
      return {
          detailsAreVisible: false,
           friend:{
                id: 'robert',
                name: 'Robert Naboj',
                phone: '0748 000 111',
                email: 'robertn@localhost.com'

            },
      };
  },
  methods: {
      toggleDetails(){
          this.detailsAreVisible = !this.detailsAreVisible;
        
        }
  }
};
</script>
<template>
    <section>
        <header>
          <h1>My Friends</h1>
          </header>
          <new-friend @add-contact="addContact"></new-friend>
        <ul>
           <friend-contact
                v-for="friend in friends"
                :key="friend.id"
                :id="friend.id"
                :name="friend.name"
                :phone-number="friend.phone"
                :email-address="friend.email">
           </friend-contact>
        </ul>
    </section>
</template>

<script>
export default {
    data() {
        return {
        friends: [
            {
                id: 'robert',
                name: 'Robert Naboj',
                phone: '0748 000 111',
                email: 'robertn@localhost.com'

            },
            {
                id: 'grzegorz',
                name: 'Grzegorz Grycar',
                phone: '0748 000 222',
                email: 'grzegorzg@localhost.com'

            }
        ]
    };
  },
  methods: {
    addContact(name, phone, email){
      const newFriendContact = {
        id: new Date().toISOString(),
        name: name,
        phone: phone,
        email: email
      };
      this.friends.push(newFriendContact);
    }
  },
};
</script>

<style>
* {
  box-sizing: border-box;
}

html {
  font-family: 'Jost', sans-serif;
}

body {
  margin: 0;
}

header {
  box-shadow: 0 2px 8px rgba(0, 0, 0, 0.26);
  margin: 3rem auto;
  border-radius: 10px;
  padding: 1rem;
  background-color: #58004d;
  color: white;
  text-align: center;
  width: 90%;
  max-width: 40rem;
}

#app ul {
  margin: 0;
  padding: 0;
  list-style: none;
}

#app li,
#app form {
  box-shadow: 0 2px 8px rgba(0, 0, 0, 0.26);
  margin: 1rem auto;
  border-radius: 10px;
  padding: 1rem;
  text-align: center;
  width: 90%;
  max-width: 40rem;
}

#app h2 {
  font-size: 2rem;
  border-bottom: 4px solid #ccc;
  color: #58004d;
  margin: 0 0 1rem 0;
}

#app button {
  font: inherit;
  cursor: pointer;
  border: 1px solid #4994e9;
  background-color: #4994e9;
  color: white;
  padding: 0.05rem 1rem;
  box-shadow: 1px 1px 2px rgba(0, 0, 0, 0.26);
}

#app button:hover,
#app button:active {
  background-color: #4a4757;
  border-color: #4a4757;
  box-shadow: 1px 1px 4px rgba(0, 0, 0, 0.26);
}

#app input {
  padding: 0.15rem;
  font: inherit;
}
#app label {
  font-weight: bold;
  margin-right: 1rem;
  width: 7rem;
  display: inline-block;
}
#app form div {
  margin: 1rem 0;
}

</style>


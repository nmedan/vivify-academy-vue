<template>
    <div>
        <h1>Contact list</h1>
            <label>Name: </label>
            <input v-model="newContact.name" type="text" placeholder="Name"><br>
            <label>Email: </label>
            <input v-model="newContact.email" type="text" placeholder="Email"><br>
            <button type="submit" @click="AddContact">Add contact</button>
        </form>
        <table>
            <thead>
                <th>Name</th>
                <th>Email </th>
            </thead>
            <tbody>
                 <tr v-for="(contact, key) in contacts" :key="key">
                      <td>{{contact.name}}</td>
                      <td>{{contact.email}}</td>
                 </tr>
            </tbody>
        </table>
    </div>
</template>

<script>
export default {
  name: 'ContactList',
  data() {
      return {
          contacts:[
              {name: "John", email: "example@gmail.com"},
              {name: "Jack", email: "example2@gmail.com"}
          ],
          newContact: {
              name: '',
              email: ''
          }
      };
    },
          methods: {
              AddContact() {
                  console.log(this.newContact);
                  this.contacts.push(this.newContact);
                  this.newContact = {};
              }
          }
      
 
}
</script>
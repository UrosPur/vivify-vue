<template>
    <div>

        <form @submit.prevent="saveContact">

            <label>First Name</label>
            <input v-model="newContact.firstName" type="text" placeholder="First Name">

            <label>Last Name</label>
            <input v-model="newContact.lastName" type="text" placeholder="Last Name">

            <label>Email</label>
            <input v-model="newContact.email" type="email" placeholder="email"/>

            <button  type="submit">Add Contact</button>

        </form>


        It works!

        <table>

            <thead>

            <th>First Name</th>
            <th>Last Name</th>
            <th>Email</th>
            <th>$nbsp:</th>
            </thead>

            <tbody>
            <tr v-for="(contact,key) in contacts" :key="key">

                <td>{{ contact.firstName }}</td>
                <td>{{ contact.lastName }}</td>
                <td>{{ contact.email }}</td>
                <td><button @click="deleteContact(contact)">Remove</button></td>
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
                contacts: [

                    {
                        firstName: 'Mirko',
                        lastName: 'Mirkovic',
                        email: 'mirko@gmail.com',
                    },
                    {
                        firstName: 'Marko',
                        lastName: 'Markovic',
                        email: 'marko@gmail.com'
                    },
                    {
                        firstName: 'Pero',
                        lastName: 'Petrovic',
                        email: 'pero@gmail.com'
                    },
                    {
                        firstName: 'Sima',
                        lastName: 'Simic',
                        email: 'sima@gmail.com'
                    },

                ],

                newContact:{

                    firstName: '',
                    lastName: '',
                    email: '',
                }

            }

        },

        methods: {
            saveContact(){

                this.contacts.push(this.newContact)

                this.newContact = {}

            },

            deleteContact(contact){

                this.contacts.splice(this.contacts.indexOf(contact), 1)

            }

        }


    }
</script>

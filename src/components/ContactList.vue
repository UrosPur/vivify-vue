<template>
    <div>
        It works!

        <table>

            <thead>

            <th>First Name</th>
            <th>Last Name</th>
            <th>Email</th>
            </thead>

            <tbody>
            <tr v-for="(contact,key) in contacts" :key="key">
            <td>{{ contact.firstName }}</td>
            <td>{{ contact.lastName }}</td>
            <td>{{ contact.email }}</td>
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

                ]

            }
        }
    }
</script>

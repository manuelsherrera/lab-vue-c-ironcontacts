<template>

  <h1>IRONCONTACTS</h1>
  <button>Add Random Contact</button>
  <table>
    <tbody>
      <tr>
        <td>Picture</td>
        <td>Name</td>
        <td>Popularity</td>
        <td>Won Oscar</td>
        <td>Won Emmy</td>
      </tr>
      <tr v-for="(item, index) of topFive">

        <td><img :src="item.pictureUrl" width="60" alt=""></td>
        <td>{{ item.name }}</td>
        <td>{{ item.popularity }}</td>
        <td><i class="fas fa-trophy" v-if="item.wonOscar"></i></td>
        <td><i class="fas fa-trophy" v-if="item.wonEmmy"></i></td>


      </tr>
    </tbody>
  </table>
</template>

<script>
import CONTACTS from "./contacts.json/"
export default {
  data() {
    return {
      contacts: CONTACTS,

    }
  },
  computed: {
    topFive() {
      return this.contacts.slice(0, 5)
    },
    remainingContact() {

      return this.contacts.slice(6)
    },
  },
  methods: {

  },

}
</script>

<style scoped>
li {
  list-style-type: none;
}
</style>



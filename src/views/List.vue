<template>
  <div class="about">
    <h1>This is an list page</h1>
    <input type="text" v-model="newContact">
    <button @click="addContact">Add Contact</button>
    <button @click="sortContact">Sort</button>

    <transition-group name="slide-up" tag="ul" appear>
      <li 
        v-for="contact in contacts"
        :key="contact"
      >
        {{ contact }}
      </li>
    </transition-group>
  </div>
</template>

<script>
export default {
  data(){
    return {
      newContact:"",
      contacts:["Naser Ahadi", "Ali Ghandehari", "Vahid Rastgoo"]
    }
  },
  methods:{
    addContact(){
      this.contacts.push(this.newContact);
      this.newContact=""
    },
    sortContact(){
      this.contacts.sort()
    }
  }
}
</script>

<style scoped>
li{
  list-style: none;
}
</style>

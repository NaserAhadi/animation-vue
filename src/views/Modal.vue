<template>
  <div class="home">
    <h1>This is Modal Page</h1>
    <button class="button" @click="showTheBox">Open</button>
    <transition name="fade">
      <div class="close-container" v-if="isShow">
        <button 
          class="button clase-button"
          @click="hideTheBox"
        >
          Close
        </button>
      </div>
    </transition>
  </div>
</template>

<script>
// @ is an alias to /src

export default {
  name: 'Modal',
  data(){
    return{
      isShow: false
    }
  },
  methods:{
    showTheBox(){
      this.isShow = true
    },
    hideTheBox(){
      this.isShow = false
    }
  }
}
</script>

<style scoped>
.button {
  outline: none;
  border-radius: 0.3rem;
  background-color: #333;
  color: #fff;
  border: none;
  padding: 0.2rem 0.5rem;
  cursor: pointer;
}

.close-container {
  background-color: #ccc;
  margin: 2rem auto;
  width: 12rem;
  height: 12rem;
  display: flex;
  justify-content: center;
  align-items: center;
  border-radius: 1rem;
}

.clase-button {
  background-color: coral;
}
</style>

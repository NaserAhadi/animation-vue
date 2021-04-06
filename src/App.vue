<template>
  <div id="app">
    <div id="nav">
      <router-link to="/">Modal</router-link> |
      <router-link to="/list">List</router-link> |
      <router-link to="/drawer">Drawer</router-link>
    </div>
    <transition name="slide-fade" mode="out-in">
      <router-view/>
    </transition>
  </div>
</template>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

#nav {
  padding: 30px;
}

#nav a {
  font-weight: bold;
  color: #2c3e50;
}

#nav a.router-link-exact-active {
  color: #42b983;
}
/*** TRANSITIONS ***/
.fade-enter {
  opacity:0
}

.fade-enter-active,
.fade-leave-active{
  transition:opacity 0.5s ease-out
}

.fade-leave-to {
  opacity: 0;
}

.slide-fade-enter {
  opacity:0;
  transform: translateX(50px)
}

.slide-fade-enter-active,
.slide-fade-leave-active{
  transition:all 0.5s ease
}

.slide-fade-leave-to {
  opacity: 0;
  transform: translateX(-50px)
}

.slide-up-enter {
  transform:translateY(10px)
}

.slide-up-enter-active{
  transition:all 0.5s ease-out
}

.slide-up-move {
  transition:transform 0.8s ease-in;
}
</style>

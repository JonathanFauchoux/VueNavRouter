<template>
  <div id="app">
    <NavBar />
      <main class="content">
        <transition name="slide" mode="out-in">
          <router-view></router-view>
        </transition>
      
    </main>
  </div>
</template>

<script>
import NavBar from './components/NavBar.vue'


export default {
  name: 'App',
  components: {
    NavBar,
    
  }
}
</script>

<style>
*{
  margin: 0;
  padding: 0;
  font-family: Helvetica, sans-serif;
}
#app {
  z-index: -1;
  color: White;
  width: 100%;
  height: 100vh;
  background: linear-gradient(
    rgba(255,255,155, .45),
    rgba(0,200,0, .45)),
    url("https://images.unsplash.com/photo-1570142056130-9f6b59c6287a?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=crop&w=1650&q=80") center no-repeat;
    background-size: cover;
}
.content{
 
  display: flex;
  align-items: center;
}

.container{
  display: flex;
  justify-content: center;
  align-items: center;
  position: absolute;
  top: 0;
  bottom: 0;
  
  width: 100%;
  height: 100%;
  
}
/* Transition */

  .slide-leave-active{
    transition: opacity .5s ease;
    opacity: 0;
    animation: slide-out .5s ease-out forwards;
  }
  .slide-leave{
    opacity: 1;
    transform: translateX(0);
  }
  .slide-enter-active{
    animation: slide-in .5s ease forwards;
    
  }

  @keyframes slide-out {
    0% {
      transform: translateY(0);
    }
    100%{
      transform: translateY(-30px);
    }
  }
  @keyframes slide-in {
    0% {
      transform: translateY(-30px);
    }
    100%{
      transform: translateY(0);
    }
  }

</style>

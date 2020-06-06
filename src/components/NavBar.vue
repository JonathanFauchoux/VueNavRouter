<template>
  <div class="container">
    <nav class="navbar" :class="{ change : isActive }" @click=" isActive = !isActive">
      <div class="burger-menu">
        <div class="line line-1"></div>
        <div class="line line-2"></div>
        <div class="line line-3"></div>
      </div>

      <ul class="nav-list">
        <router-link to="/" tag="li"  active-class="active" exact class="nav-item"><a class="nav-link">Home</a></router-link>
        <router-link to="/Why" tag="li"  active-class="active" exact class="nav-item"><a class="nav-link">Why?</a></router-link>
        <router-link to="/About" tag="li" active-class="active" class="nav-item"><a class="nav-link">About</a></router-link>
        <router-link to="/Contact" tag="li" active-class="active" class="nav-item"><a class="nav-link">Contact</a></router-link>
      </ul>
    </nav>
    
  </div>
</template>

<script>
export default {
  name: 'NavBar',
  data : () => {
    return {
      navbar : document.querySelector('.navbar'),
      isActive: true,
    }
  },
  methods:{
    
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style >
.navbar{
  z-index: 1;
  width: 6rem;
  height: 18rem;
  background-color: rgba(186, 218, 85, .55);

  position: fixed;
  top:10%;
  right: -360px;

  display: flex;
  justify-content: center;
  align-items: center;
  border-radius: 55rem 0 0 55rem;

  transition: right .8s cubic-bezier(1,0,0,1);

  box-shadow: 10px 10px 18px 7px rgba(0, 0, 0, 0.75);

}

/* Burgerrr */

  .burger-menu{
    display: flex;
    flex-direction: column;
    justify-content: space-around;

    width: 30px;
    height: 25px;
    
    position: fixed;
    top: 1rem;
    right: 1rem;
    cursor: pointer;
  }
  .line{
    width: 100%;
    height: 3px;
    background-color: white;
    transition: all .6s ;

  }
  .change{
    right: 0;
  }
  .change .line-1{
    transform: rotateZ(-405deg) translate(-7px, 6px);
  }
  .change .line-2{
    opacity: 0;
  }
  .change .line-3{
    transform: rotateZ(405deg) translate(-5px, -6px);
  }

/* nav */

  .nav-list{
    text-align: left;
    width: 100%;
    padding-left: 1.3rem;
  }
  .nav-item{
    display: flex;
    list-style: none;
    margin: 1rem 0;
    min-width: 100%;
    
    
  }
  .nav-link{
    text-decoration: none;
    width: 100%;
    font-size: .75rem;
    text-transform: uppercase;
    color: white;
    font-weight: 300;
    position: relative;
    padding: 3px 0;

  }

  .nav-link::before, .nav-link::after {
    content: "";
    width: 100%;
    height: 2px;
    background-color: white;
    position: absolute;
    left:0;
    transform: scaleX(0) ;
    transition: all 0.5s;
  }
  .nav-link::after{
    bottom: 0;
    transform-origin: right;
  }
  .nav-link::before{
    top: 0;
    transform-origin: left;
  }

  .nav-link:hover{
    color: #2c3e50 ;
    
  }

  .nav-link:hover::before, .nav-link:hover::after {
    transform: scaleX(1) ;
  }

  .active>a{
    background: white;
    color: #BADA55;
    padding: .2rem 1rem;
    max-width: 100%;

  }

</style>

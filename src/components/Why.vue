<template>
  <div class="container why">
    
    <div class="why__head">
      <h2 class="title">Why?</h2>
      <p>Lorem ipsum dolor sit amet consectetur.</p>
    </div>
    <a class="toContactBtn" @click="navigateToHome">Contact Me!</a>
  </div>
</template>

<script>
export default {
  name: 'Why',
  data : () => {
    return {
      
    }
  },
  methods: {
    navigateToHome(){
      this.$router.push('/Contact')
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style >
.why{
  flex-direction: column ;
  align-items: center;;
  width: 100%;
  
}
.why__head{
  padding: 5rem;
}
.toContactBtn{
  
  padding: 1rem 2rem;
  border: 1px solid white;
  border-radius: 1rem;
  text-transform: uppercase;
  font-weight: 600;
  letter-spacing: 2px;;
  color: white;
  background-color: rgba(186, 218, 85, .55);
}

</style>

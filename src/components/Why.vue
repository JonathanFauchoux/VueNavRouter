<template>
  <div class="container why">
    
    <div class="why__head">
      <h2 class="title">Why?</h2>
      <p>Lorem ipsum dolor sit amet consectetur.</p>
    </div>
    <Button @click="navigateToHome">Contact Me!</Button>
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
  margin-bottom: 5rem;
}
.why__head{
  padding: 5rem;
}
button{
  width: 5rem;
}

</style>

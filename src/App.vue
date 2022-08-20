<template>
 <div class="main-container">
   <div class="left-container">
    <div class="container">
      <Signup></Signup>
      <Term></Term>
    </div>
  </div>
  <div class="right-container">
        <HaveAccount></HaveAccount>
  </div>
 </div>
</template>

<script>
  import Signup from './components/Signup.vue'
  import Term from './components/Term.vue'
  import HaveAccount from './components/HaveAccount.vue';
  

  export default {
    name: 'App',
    components: {
    Term,
    Signup,
    HaveAccount
}
  }
</script>

<style scoped>

  

  
  .main-container{
    display: flex;
    min-height: 100vh;

  }
  .left-container{
    display: flex;
    flex-direction: column;
    width: 50%;
  }

  .left-container{
    display: flex;
    width: 50%;
  }
  .container{
    margin: auto;
  }

</style>

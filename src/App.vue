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

  .right-container{
    display: flex;
    flex-direction: column;

    width: 50%;
  }


  .container{
    margin: auto;
  }

  @media (max-width:320px) {
    .left-container{
      width:100%;
    }

    .right-container{
      width:100%;
    }

    .main-container{
      flex-direction: column;
      gap: 40px;
    }

    .container{
      width:75%;
      margin: 25px;
    }

    
  }
  @media (min-width:320px) and (max-width:375px) {
    .left-container{
      width:100%;
    }

    .right-container{
      width:100%;
    }

    .main-container{
      flex-direction: column;
      gap: 40px;
    }

    .container{
      width:75%;
      margin: 25px;
    }

    
  }
  @media (min-width:375px) and (max-width:426px) {
    .left-container{
      width:100%;
    }

    .right-container{
      width:100%;
    }

    .main-container{
      flex-direction: column;
      gap: 40px;
    }

    .container{
      width:75%;
      margin: 25px;
    } 
  }
  @media (min-width:426px) and (max-width:768px) {
    .left-container{
      width:100%;
    }

    .right-container{
      width:100%;
    }

    .main-container{
      flex-direction: row;
      gap: 40px;
    }

    .container{
      width:75%;
      margin: auto;
      
    } 
  }
  @media (min-width:768px) and (max-width:1024px) {
    .left-container{
      width:100%;
    }

    .right-container{
      width:100%;
    }

    .main-container{
      flex-direction: row;
      gap: 40px;
    }

    .container{
      width:75%;
      margin: auto;
      
    } 
  }
  

</style>

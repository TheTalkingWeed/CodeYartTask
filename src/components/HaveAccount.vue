<template>
    <div class="main-container">
        <div class="text-container">
                <img src="../assets/images/acme.png" alt="" class="acme-img">
                <h2>Do you already have an account?</h2>
                <h4>That's awesome! You can login by clicking on the  button below. To skip next time, you can ask us to remember your login credentials.</h4>
                <Button class="login-btn" text="Log in"></Button>
            </div>
    </div>
</template>

<script>
    import Button from './Button.vue'



export default {

    name: 'have-account',

    components:{
        Button
    }
}
</script>

<style scoped>

    @import url('https://fonts.googleapis.com/css2?family=Open+Sans&display=swap');


    .main-container{
        position: relative;
        display:flex;
        width: 100%;
        background: url("../assets/background/background.jpg") no-repeat fixed top;
        background-size: cover;
    }

    

    
    

    .text-container{
        display: flex;
        flex-direction: column;
        width: 60%;
        margin:60px auto auto auto;
    }

    

    .text-container h2{
        font-family: 'Open Sans', sans-serif;
        color: #FFFFFF;
        width:80%;
        letter-spacing: 2px;
        line-height: 44px;
        font-size: 30px;
    }

    .text-container h4{
        margin:0;
        font-family:-apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Oxygen, Ubuntu, Cantarell, 'Open Sans', 'Helvetica Neue', sans-serif;
        color: #FFFFFF;
        font-size: 14px;
        letter-spacing: 1px;
        line-height: 30px;
        font-weight: 100;
    }

    .acme-img{
        width: 25%;
        margin-bottom:30px;
    }

    .login-btn{
        margin-top:20px;
        background: transparent;
        border: 2px solid #FFFFFF;
        transition: .3s;
        font-weight: 600;
        line-height: 30px;
    }

    .login-btn:hover{
        background-color: #FFFFFF;
        color:black;
    }


   
</style>
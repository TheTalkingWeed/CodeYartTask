<template>
    <button class="sign-up-button">{{text}}</button>    
</template>

<script>
export default {
    name : 'signup-button',

    props:{
        text:String
    }
}
</script>

<style scoped>
    .sign-up-button{
        background-color: #4a90e2;
        border:none;
        border-radius: 5px;
        color:#ffffff;
        padding: auto 8 auto 8 ;
        font-size: 17px;
        width:120px;
        height: 48px;
        cursor: pointer;
    }
   
</style>
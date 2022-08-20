<template>
    <div class="bottom-container">
        
            <p>© 2015 Acme, Inc.</p>
            <label class="link-item">Terms</label>
            <label class="link-item">Privacy</label>
            <label class="dots">...</label>
        
            
    </div>    
</template>

<script>
export default {
    name: 'term-component'
}
</script>

<style scoped>
    @import url('https://fonts.googleapis.com/css2?family=Open+Sans&display=swap');

    .bottom-container{
        position: absolute;
        margin-top:30px;
        display: flex;
        gap: 10px;
        align-items: center;
        font-family: 'Open Sans', sans-serif;
        color: #a1a1a1;

    }

    p{
        font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Oxygen, Ubuntu, Cantarell, 'Open Sans', 'Helvetica Neue', sans-serif;
        font-size: 12px;
        line-height: 15px;

    }
   
    .link-item{
        font-size:12px;
        line-height: 17px;
        font-weight: 600;
        cursor: pointer;
    }

    .dots{
        position: absolute;
        left: 103%;
        top:-25%;
        font-size:30px;
        font-weight: 600;
        letter-spacing: 2px;
        cursor: pointer;
    }




  

    



</style>
<template>
    <div class="strength-bar" >
        <div class="strong" id="strong"></div>
        <div class="good" id="good"></div>
        <div class="medium" id="medium"></div>
        <div class="weak" id="weak"></div>
    </div>
</template>

<script>

    export default {
        name: 'strength-bar',
        props: {
            strength:String
        },

        methods:{
            setStrength(){
                const strongdiv = document.getElementById('strong');
                const gooddiv = document.getElementById('good');
                const mediumdiv = document.getElementById('medium');
                const weakdiv = document.getElementById('weak');
                this.strength === 'strong' ? (
                  strongdiv.style.backgroundColor='#50C878',
                  gooddiv.style.backgroundColor='#FFEA00',
                  mediumdiv.style.backgroundColor='#F9C466',
                  weakdiv.style.backgroundColor='#CD4146'
                ) : this.strength === 'good' ? (
                  strongdiv.style.backgroundColor='#d4d4d4',
                  gooddiv.style.backgroundColor='#FFEA00',
                  mediumdiv.style.backgroundColor='#F9C466',
                  weakdiv.style.backgroundColor='#CD4146'
                ) : this.strength === 'medium' ? (
                  strongdiv.style.backgroundColor='#d4d4d4',
                  gooddiv.style.backgroundColor='#d4d4d4',
                  mediumdiv.style.backgroundColor='#F9C466',
                  weakdiv.style.backgroundColor='#CD4146'
                ) : this.strength === 'weak' ? (
                  strongdiv.style.backgroundColor='#d4d4d4',
                  gooddiv.style.backgroundColor='#d4d4d4',
                  mediumdiv.style.backgroundColor='#d4d4d4',
                  weakdiv.style.backgroundColor='#CD4146'
                ) :  (
                  strongdiv.style.backgroundColor='#d4d4d4',
                  gooddiv.style.backgroundColor='#d4d4d4',
                  mediumdiv.style.backgroundColor='#d4d4d4',
                  weakdiv.style.backgroundColor='#d4d4d4'
                )
            }
        },

        updated(){
            if(this.strength){
                this.setStrength()
            }
        }


    }
</script>

<style scoped>

    .strength-bar{
        width:10px;
        display: flex;
        flex-direction: column;
    }
    .strength-bar div{
        margin: 2px;
        padding: 0;
        width: 4px;
        height: 4px;
        border-radius: 50px;
        background-color: #d4d4d4;

    }

</style>
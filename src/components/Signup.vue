<template>

    <div class="signup-container">
        <div class="top-text">
            <h1>Welcome to Acme.</h1>
            <h6>Create yout account by filling the form below.</h6>
        </div>

        <div class="form">
             <input type="text" id="email" autocomplete="off"   required />
            <label for="email" class="label-name" id="input-label">
                <span class="content-name" >
                  Email
                </span>
            </label>
        </div>
        <div class="form">
            <i class="open-eye" id="toggle-reveal" @click="revealPass" ></i>
            <StrengthBar class="strength-bar" :strength="strength"></StrengthBar>
            <input type="password" id="password" autocomplete="off"  @keyup="checkStrength"  class="passin" required />
            <label for="password" class="label-name">
                <span class="content-name">
                    Password
                </span>
            </label>
        </div>

        <div class="remember-me-container">
            <input type="checkbox" id="remember-me" name="check">
            <label @click = "check">Remember me.</label>
        </div>


        <Button class="sign-up-btn" text="Sign up" @btn-clicked="getUserInputs"> </Button>
    </div>
</template>

<script>
    import Button from './Button.vue'
    import StrengthBar from './StrengthBar.vue';
    export default {
        name :'signup-form',

        data(){
            return{
                strength:"",
                userinput:{
                    email: "",
                    password:""
                }
            }
        },

        components:{
            Button,
            StrengthBar
        },

        methods: {
            check(){
                const checkb = document.getElementById('remember-me')
                checkb.checked = !checkb.checked;
            },

            revealPass(){
                const eye = document.getElementById('toggle-reveal');
                const passfield = document.getElementById('password');
                passfield.type = passfield.type === 'password' ? 'text' : 'password';
                eye.classList.toggle("closed-eye");
            },

            checkStrength(){
                const passinput = document.getElementById('password');
                var str = 0;
                var output = 'none';

                var lowerCaseLetters = /[a-z]/g;
                if (passinput.value.match(lowerCaseLetters)) {
                    str++;
                }

                var upperCaseLetters = /[A-Z]/g;
                if (passinput.value.match(upperCaseLetters)) {
                    str++;
                } 

                var numbers = /[0-9]/g;
                if (passinput.value.match(numbers)) {
                    str++;
                }

                if (passinput.value.length >= 8) {
                    str++   ;
                }

                if (passinput.value.length === 0){
                    output = 'none'
                }
                     
                output = str === 1 ? 'weak' :
                         str === 2 ? 'medium':
                         str === 3 ? 'good':
                         str === 4 ? 'strong' : 'none'
                
                this.strength = output
            },

            getUserInputs(){

                const emailinput = document.getElementById('email')
                const passwordinput = document.getElementById('password')

                this.userinput.email = emailinput.value
                this.userinput.password = passwordinput.value
                
                this.$emit('get-userinput',this.userinput)

                emailinput.value = null
                passwordinput.value = null
                this.strength = 'none'
            }

            
            

        }
}
</script>

<style scoped>
    @import url('https://fonts.googleapis.com/css2?family=Open+Sans&display=swap');

    

    .signup-container{
        display: flex;
        flex-direction: column;
        width: 400px;
        padding:35px;
        border-radius: 10px;
        font-family: 'Open Sans', sans-serif;
        box-shadow: rgba(0, 0, 0, 0.2) 0px 0px 5px;
    }

    .top-text h1{
        color: #757575;
        font-size: 30px;
        line-height: 30px;
        margin-top:0;
        font-weight: 600;
    }

    .top-text h6{
        color: #A1A1A1;
        font-size: 14px;
        line-height: 19px;
        margin-top:0;
        font-weight: 600;
        letter-spacing: 1px;

    }

    .form {
        width: 100%;
        position: relative;
        height: 60px;
        overflow: hidden;
    }

    .form input {
        width: 100%;
        height: 100%;
        color: #757575;
        padding-top: 15px;
        background: transparent;
        font-size: 14px;
        border:none;
        line-height: 15px;
        margin-bottom:15px;
        font-family: system-ui, -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Oxygen, Ubuntu, Cantarell, 'Open Sans', 'Helvetica Neue', sans-serif;
    }
    .form label {
        position: absolute;
        bottom: 0px;
        left: 0px;
        width: 100%;
        height: 100%;
        pointer-events: none;
        border-bottom: 1px solid #A1A1A1;
    }
    .form label::after {
        content: "";
        position: absolute;
        bottom: -1px;
        left: 0px;
        width: 100%;
        height: 100%;
        border-bottom: 1px solid #A1A1A1;
        transform: translateX(-100%);
        transition: all 0.3s ease;
    }

    .content-name {
        position: absolute;
        bottom: 0px;
        left: 0px;
        opacity: 50%;
        padding-bottom: 5px;
        font-size: 12px;
        transition: all 0.3s ease;
    }
    .form input:focus {
        outline: none;
    }
    .form input:focus + .label-name .content-name,
    .form input:valid + .label-name .content-name {
        transform: translateY(-100%);
        font-size: 12px;
        left: 0px;
        color: #A1A1A1 ;
        opacity: 100%;

    }

    .form input:focus + .label-name::after,
    .form input:valid + .label-name::after {
        transform: translateX(0%);

    }

    .form input:focus + .label-name .content-name{
        color:#4A90E2;
    }
    .form input:focus + .label-name::after{
        border-bottom: 1px solid #4A90E2;
    }


    .remember-me-container{
        display: flex;
        align-items: center;
        height:25px;
        margin-top: 15px;
    }

    .remember-me-container label{
        color: #A1A1A1;
        font-size: 14px;
        line-height: 17px;
        margin-top:auto;
        cursor:pointer;
        user-select: none;
    }

    .remember-me-container input[type=checkbox] {
        position:relative;
        cursor: pointer;
        margin-right: 17px;
    }

    input[type=checkbox]:before {
        content: "";
        display: block;
        position: absolute;
        width: 20px;
        height: 20px;
        top: 0;
        left: 0;
        background-color:#e9e9e9;
    }

    input[type=checkbox]:checked:before {
         content: "";
         display: block;
         position: absolute;
         width: 20px;
         height: 20px;
         top: 0;
         left: 0;
         background-color:#1E80EF;
    }

    input[type=checkbox]:checked:after {
         content: "";
         display: block;
         width: 5px;
         height: 10px;
         border: solid white;
         border-width: 0 2px 2px 0;
         -webkit-transform: rotate(45deg);
         -ms-transform: rotate(45deg);
         transform: rotate(45deg);
         position: absolute;
         top: 2px;
         left: 6px;
    }

    .open-eye{
        content: url('../assets/images/fa-eye.png');
        position: absolute;
        top:60%;
        left:90%;
        cursor: pointer;
    }

    .closed-eye{
       content: url('../assets/images/fa-eye-slash.png');
        position: absolute;
        top:60%;
        left:90%;
        cursor: pointer;
    }

    .sign-up-button{
        position:relative;
        margin-right: 0;
        margin-left: auto;
        margin-top:25px;
        font-weight: 600;
        transition: .3s;
    }

     .sign-up-button:hover{
        background-color: #3f7bc0;


    }

    .strength-bar{
        position: absolute;
        left:98%;
        top:40%;
        margin:0;
        z-index: 50;
    }

      @media (max-width:320px){
        .signup-container{
            width:85%;
            margin:0;
        }

        .sign-up-button{
            margin:auto;
            margin-top: 25px;
        }

        .strength-bar{
            left:98%;
        }

        .open-eye{
            left:85%;
        }

        .closed-eye{
            left:85%;
        }

      }
      @media (min-width:320px) and (max-width:375px){
        .signup-container{
            width:90%;
            margin:0;
        }

        .sign-up-button{
            margin:auto;
            margin-top: 25px;
        }

        .strength-bar{
            left:96%;
        }

        .open-eye{
            left:85%;
        }

        .closed-eye{
            left:85%;
        }

      }
      @media (min-width:375px) and (max-width:426px){
        .signup-container{
            width:95%;
            margin:0;
        }

        .sign-up-button{
            margin:auto;
            margin-top: 25px;
        }

        .strength-bar{
            left:97%;
        }

        .open-eye{
            left:88%;
        }

        .closed-eye{
            left:88%;
        }

      }
      @media (min-width:426px) and (max-width:768px){
        .signup-container{
            width:95%;
            margin:0;
        }

        .sign-up-button{
            margin:auto;
            margin-top: 25px;
        }

        .strength-bar{
            left:98%;
        }

        .open-eye{
            left:93%;
        }

        .closed-eye{
            left:93%;
        }

      }
      @media (min-width:768px) and (max-width:1024px){
        .signup-container{
            width:90%;
            margin:0;
        }

        .sign-up-button{
            margin:auto;
            margin-top: 25px;
        }

        .strength-bar{
            left:97%;
        }

        .open-eye{
            left:88%;
        }

        .closed-eye{
            left:88%;
        }

      }
      
    


</style>
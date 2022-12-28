<template>
  <div class="wrapper">
    <Header/>
<h1>Contactez nous</h1>
<div v-if="isFormCorrect">
<div class="success">
  <h1>Votre message a bien été envoyé</h1>
<span class="icon">  <font-awesome-icon  icon="far fa-check-circle" /></span>

</div>
</div>
<div v-else id="container">
 

  <form ref="form" @submit.prevent="handleSubmit" id="contact_form">
    <div class="name">
      <label for="firstname"></label>
        <div v-if="v$.firstname.$error" class="error"> <input type="text" placeholder="Ce champ est obligatoire." name="firstname" id="firstname" v-model="firstname" @blur="v$.firstname.$touch" required ></div>
          <div v-else>      <input type="text" placeholder="Prénom" name="firstname" id="firstname" v-model="firstname" @blur="v$.firstname.$touch" required >
</div>

    </div>
    
    <div class="email">
      <label for="lastname"></label>
  <div v-if="v$.firstname.$error" class="error"> <input type="text" placeholder="Ce champ est obligatoire." name="email" id="email" v-model="firstname" @blur="v$.email.$touch" required ></div>
          <div v-else>      <input type="text" placeholder="Nom de famille" name="lastname" id="lastname" v-model="lastname" @blur="v$.lastname.$touch" required >    </div>
    </div>
       <div class="name">
      <label for="telephone"></label>
  <div v-if="v$.tel.$error" class="error"> <input type="tel" placeholder="Numéro invalide." name="telephone" id="telephone" v-model="tel" @blur="v$.tel.$touch" required ></div>
          <div v-else>      <input type="tel" placeholder="telephone" name="telephone" id="telephone" v-model="tel" @blur="v$.tel.$touch" required >    </div>
    </div>
      <div class="email">
      <label for="email"></label>
  <div v-if="v$.firstname.$error" class="error"> <input type="text" placeholder="email invalide." name="email" id="email" v-model="firstname" @blur="v$.email.$touch" required ></div>
          <div v-else>      <input type="email" placeholder="Email" name="email" id="email" v-model="email" @blur="v$.email.$touch" required >    </div>
    </div>

    <div class="telephone">
      <label for="company"></label>
      <div class="telephone">
      <label for="business"></label>
  <div v-if="v$.business.$error" class="error"> <input type="text" placeholder="ce champ obligatoire." name="business" id="business" v-model="business" @blur="v$.business.$touch" required ></div>
          <div v-else>      <input type="text" placeholder="nom de la société" name="business" id="business" v-model="business" @blur="v$.business.$touch" required >    </div>
    </div>    </div>
  
    <div class="message">
      <label for="message"></label>

       <div v-if="v$.message.$error" class="error"> <textarea name="message" placeholder="ce champ est obligatoire." id="message_input" cols="30" rows="5" required v-model="message" @blur="v$.message.$touch" ></textarea></div>
          <div v-else>      <textarea name="message" placeholder="message" id="message_input" cols="30" rows="5" required v-model="message" @blur="v$.message.$touch" > </textarea>   </div>
    </div>
    <div class="submit">
      <input type="submit" value="Envoyer" id="form_button"  @click="send" />
    </div>
  </form><!-- // End form -->
</div><!-- // End #container -->
    <div class="container-infos">
        <div class="text">
<h1>Contactez nous</h1>
<p>Vous pouvez nous contacter par mail, téléphone ou en remplissant le formulaire ci-dessus.</p>


 <div class="address">
          <div class="info">
<font-awesome-icon  icon="fas fa-mobile-alt" /> 
  <span><a href="tel:+33659288570"> +33 6 59 28 85 70</a></span>
  </div>
       <div class="info">
<font-awesome-icon  icon="far fa-clock" /> 
  <span>Lundi au Samedi : 7h - 19h</span>
  </div>


   <div class="info">
<font-awesome-icon  icon="fas fa-envelope" />
  <span>Niantandemolition@gmail.com</span>
  </div>
     <div class="info">
<font-awesome-icon  icon="fas fa-map-marker-alt" />
  <span>45 bis Boulevard Davout, 75020 Paris</span>
  </div>
        <div class="info">
<font-awesome-icon  icon="fas fa-subway" /> <span>Stations Porte de Montreuil ou Porte de Vincennes</span>
  </div>
        
    </div>
        </div>

            <iframe class="map" src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d2625.382407658975!2d2.411002513585662!3d48.85091788134698!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x47e6727e19d6e61b%3A0x5d3218b5f9fdc607!2s45%20Bd%20Davout%2C%2075020%20Paris!5e0!3m2!1sfr!2sfr!4v1667895568309!5m2!1sfr!2sfr" width="600" height="450" style="border:0;" allowfullscreen="" loading="lazy" referrerpolicy="no-referrer-when-downgrade" title="niantan-demolition-location"></iframe>  
            

    </div>
    <Footer/>
  </div>
</template>

<script>
import { useVuelidate } from '@vuelidate/core'
import Footer from '@/components/Footer.vue'
import Header from '@/components/Header-content.vue'

import { required, email, alpha, numeric, alphaNum } from '@vuelidate/validators'

export default {
  setup () {
    return { v$: useVuelidate() }
  },
  components:{Footer,Header},
  data () {
    return {
      firstname: '',
      lastname: '',
        email: '',
        tel:'',
        message:'',
        business:'',
        isFormCorrect:"",
                     submitted: false

    }
  },
  validations () {
    return {
      firstname: { required }, // Matches this.firstName
      lastname: { required }, // Matches this.lastName
        email: { required,email }, // Matches this.contact.email
        business: { required }, // Matches this.lastName
      message: { required }, // Matches this.lastName
      tel: { numeric,required }, // Matches this.lastName


  
    }
  },
    created() {
            setTimeout(() => this.isFormCorrect = false, 1000)
        },
        
    mounted(){
      window.scrollTo(0,0)
    },
   methods: {
           async send() {
                this.submitted = true;
const isFormCorrect = await this.v$.$validate();
this.isFormCorrect = isFormCorrect

/*if (isFormCorrect==true) {
emailjs.sendForm('service_qx8ql38', 'template_wlflq6g', this.$refs.form, 'iMSRNYA0xKflKPitU')
        .then((result) => {
            console.log('SUCCESS!', result.text);
        }, (error) => {
            console.log('FAILED...', error.text);
        });}

 
    
*/ 


      // you can show some extra alert to the user or just leave the each field to show it's `$errors`.
      if (!isFormCorrect) return console.log('error')
            }
        }
}
</script>

<style lang="scss" scoped>


.wrapper{
    background-color: rgb(232, 238, 247);

}
h1{

    padding: 20px 0;
}
.error{

  ::placeholder{
        color: red;

  }
}
.container-infos {
display: grid;
grid-template-columns: repeat(4, 1fr);
grid-template-rows: 1fr;
grid-column-gap: 0px;
grid-row-gap: 0px;
}

.text { grid-area: 1 / 1 / 2 / 3;

  text-align: left;
background: #fdc23e;
padding: 20%;
            h2{
              font-size: 35px;
            }

      p{
        font-size: 20px;
        padding: 15px 0;
        line-height: 40px;
      }
         
         button{
            font-size: 20px;
            background: white;
            color: black;
            padding: 10px 40px;
            border: none;
            cursor: pointer;
         }}


.map { grid-area: 1 / 3 / 2 / 5;
  height: 100%;
  width: 100%;
}

.success{
  width: 80%;
  margin: auto;
  padding: 5%;

  .icon{
    font-size: 50px;  
    color: rgb(0, 235, 145);

  }
}
.info{
    display: flex;
    justify-content: space-between;
            margin: 15px 0;
            font-size: 20px;
            cursor: pointer;
            border-bottom: 1px solid black;


                span{
                    margin: 0 5px;
                    text-align: right;
                }
}

button {
  overflow: visible;
}

button, select {
  text-transform: none;
}

button, input, select, textarea {
  color: #5A5A5A;
  font: inherit;
  margin: 0;
}

input {
  line-height: normal;
}

textarea {
  overflow: auto;
}

#container {
  border: solid 3px #474544;
  max-width: 768px;
  margin: 60px auto;
  position: relative;
}

form {
  padding: 37.5px;
  margin: 50px 0;
}

h1 {
  color: #000000;
  font-size: 32px;
  font-weight: 700;
  letter-spacing: 7px;
  text-align: center;
  text-transform: uppercase;
}

.underline {
  border-bottom: solid 2px #474544;
  margin: -0.512em auto;
  width: 80px;
}

.icon_wrapper {
  margin: 50px auto 0;
  width: 100%;
}

.icon {
  display: block;
  fill: #474544;
  height: 50px;
  margin: 0 auto;
  width: 50px;
}

.email {
	float: right;
	width: 45%;
}

input[type='text'],input[type='tel'], [type='email'], select, textarea {
	background: none;
  border: none;
	border-bottom: solid 2px #474544;
	color: #474544;
	font-size: 1.000em;
  font-weight: 400;
  letter-spacing: 1px;
	margin: 0em 0 1.875em 0;
	padding: 0 0 0.875em 0;
  text-transform: uppercase;
	width: 100%;
	-webkit-box-sizing: border-box;
	-moz-box-sizing: border-box;
	-ms-box-sizing: border-box;
	-o-box-sizing: border-box;
	box-sizing: border-box;
	-webkit-transition: all 0.3s;
	-moz-transition: all 0.3s;
	-ms-transition: all 0.3s;
	-o-transition: all 0.3s;
	transition: all 0.3s;
}

input[type='text']:focus, [type='email']:focus, textarea:focus {
	outline: none;
	padding: 0 0 0.875em 0;
}

.message {
	float: none;
}

.name {
	float: left;
	width: 45%;
}



.subject {
  width: 100%;
}

.telephone {
  width: 100%;
}

textarea {
	line-height: 150%;
	height: 150px;
	resize: none;
  width: 100%;
}

::-webkit-input-placeholder {
	color: #474544;
}

:-moz-placeholder { 
	color: #474544;
	opacity: 1;
}

::-moz-placeholder {
	color: #474544;
	opacity: 1;
}

:-ms-input-placeholder {
	color: #474544;
}

#form_button {
  background: none;
  border: solid 2px #474544;
  color: #474544;
  cursor: pointer;
  display: inline-block;
  font-family: 'Helvetica', Arial, sans-serif;
  font-size: 0.875em;
  font-weight: bold;
  outline: none;
  padding: 20px 35px;
  text-transform: uppercase;
  -webkit-transition: all 0.3s;
	-moz-transition: all 0.3s;
	-ms-transition: all 0.3s;
	-o-transition: all 0.3s;
	transition: all 0.3s;
}

#form_button:hover {
  background: #474544;
  color: #F2F3EB;
}

@media (max-width:900px) {
  
  .container-infos{
    display: flex;
    flex-direction: column;

    .map{
      height: 350px;
    }
  }
}

@media screen and (max-width: 768px) {
  #container {
    margin: 20px auto;
    width: 95%;
  }
}

@media screen and (max-width: 480px) {
  h1 {
    font-size: 26px;
  }
  
  .underline {
    width: 68px;
  }
  
  #form_button {
    padding: 15px 25px;
  }
}

@media screen and (max-width: 420px) {
  h1 {
    font-size: 18px;
  }
  
  .icon {
    height: 35px;
    width: 35px;
  }
  
  .underline {
    width: 53px;
  }
  
  input[type='text'], [type='email'], select, textarea {
    font-size: 0.875em;
  }
}
</style>
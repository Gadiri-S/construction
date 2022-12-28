<template>
  <div>

    <!--Menu Mobile & Tablet-->
    <div class="header-mobile">

        <div class="container-first-row">

<div class="logo">
    <img src="../assets/logo2.png"  class="logo" alt="logo de l'entreprise Niantan Demolition">

</div>
<div class="menu-burger" @click="showMenu">
    <img src="../assets/burgerwhite.webp"  class="menu-burger" alt="menu burger à dérouler pour afficher le menu">
</div>
</div>
<transition name="nested">
<div v-if="show" class="nav-menu-mobile">
        <ul>
         <router-link to='/'>   <li>Accueil</li>    </router-link>      
              <li @click="nav(about[0].id)">Notre Philosophie</li>

            <li @click="nav(services[0].id)">Nos Services</li>
          <router-link to='/'>   <li>Contact</li> </router-link>    
        </ul>
    </div>
</transition>
</div> 

 
 <!--Menu Desktop-->

 <div class="header">

    <div class="logo">
        <img src="../assets/logo2.png"  class="logo" alt="">
    </div>

    <div class="nav-menu">
        <ul>
         <router-link to='/'>   <li>Accueil</li>    </router-link>      
              <li @click="nav(about[0].id)">Notre Philosophie</li>

            <li @click="nav(services[0].id)">Nos Services</li>
          <router-link to='/'>   <li>Contact</li> </router-link>    
        </ul>
    </div>

<div>
    <button><a href="tel:+33659288570"> +33 6 59 28 85 70</a></button>
</div>
 </div> 
 </div>
</template>

<script>
export default {
    data(){
        return {

                show:false,
                contact: [
   {
id: 'contact'}],
 services: [
   {
id: 'services'}],
about: [
   {
id: 'about'}],


        }
    },
    methods:{
        showMenu(){
    
            this.show = !this.show
        },
        nav(id) {

const position = document.getElementById(id).offsetTop;
  // smooth scroll
 window.scrollTo({ top: position, behavior: "smooth" });  
}
    }

}
</script>

<style lang="scss" scoped>

.header-mobile,.container-first-row{
    display: none;
}

.header{
    display: flex;
    justify-content: space-around;
    padding: 15px;
    color:white;
    animation: movedown 1s ease-in-out;
            max-width: 2000px;
margin: auto;
}
.nav-menu{
    display: flex;
    align-items: center;
    

    ul {
        
        display: flex;
        align-items: center;
        
        transition: all .4s ease;


    li{
        list-style-type:none;
        margin: 0 15px 0 15px;
        font-size: 20px;
        transition: all .4s ease;
        cursor:pointer;

        &:hover{
            color: rgb(255, 208, 0);
        }

    }
     
}
}
.logo{
    height: 25px;
    width: 53.36;
  
}

 button{
        font-size: 17px;
        padding: 10px;
        background:  rgba(0, 0, 0, 0.5);;
        border: 1px solid rgba(0, 0, 0, 0.5);
        color:rgb(255, 255, 255);
        font-weight: 400;
font-family: 'Lato', sans-serif;
              cursor:pointer;   
              transition: .4s ease-in-out;
                  border-radius: 0 25px 25px 0;

  &:hover{
    background: black;
    color: rgb(238, 214, 0);
              transition: .4s ease-in-out;
              border: 1px solid black;

  }
              
              }

                @keyframes movedown {

        0% {
            transform: translateY(-400px);
        }
        100% {
            transform: translateX(0px);
    
        }
    }
/*Responsive mobile & tablets*/ 

@media (max-width:1000px) {
    .header{
        display: none;
    }

    .header-mobile{
        display: block;

    }
    .container-first-row{
        display: flex;
        justify-content: space-around;
        padding:15px;
    }
    .menu-burger{
        height: 35px;
        width: 42px;
        cursor: pointer;
    }

    .nav-menu-mobile{

   
        ul li{
            list-style-type: none;
            font-size: 25px;
            margin: 15px 0 15px 0;
            cursor: pointer;

            &:hover{
                background: rgba(255, 255, 255, 0.274);
                transition: .5s;
            }
        }
    }

    .nested-enter-active, .nested-leave-active {
	transition: all 0.3s ease-in-out;
}
/* delay leave of parent element */
.nested-leave-active {
  transition-delay: 0.25s;
}

.nested-enter-from,
.nested-leave-to {
  transform: translateY(30px);
  opacity: 0;
}

/* we can also transition nested elements using nested selectors */
.nested-enter-active .inner,
.nested-leave-active .inner { 
  transition: all 0.3s ease-in-out;
}
/* delay enter of nested element */
.nested-enter-active .inner {
	transition-delay: 0.25s;
}

.nested-enter-from .inner,
.nested-leave-to .inner {
  transform: translateX(30px);
  /*
  	Hack around a Chrome 96 bug in handling nested opacity transitions.
    This is not needed in other browsers or Chrome 99+ where the bug
    has been fixed.
  */
  opacity: 0.001;
}
}

</style>
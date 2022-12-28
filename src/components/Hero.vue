<template>
  <div class="hero-container"> 
    <div class="container-img">
      </div>
    <Header />


    <div class="container">
     
      <div class="text">
<h1><span class="yellow-highliner">N</span>iantan <span class="yellow-highliner">D</span>emolition</h1>
<h2>Terrassement et démolition</h2>
<p>Niantan Démolition est une société spécialisée dans les travaux de démolition et de térrassement mais dispose aussi d'une expertise dans les travaux d'aménagements. Nous opérons dans toute la région d'Île-de-France.</p>

<div> <router-link to='/contact'><button>Demander un devis</button></router-link></div>
</div>



</div>

  </div>
</template>

<script>


import Header from '@/components/Header.vue'

export default {
  name: "Hero",
  components: {
    Header
  },

  data() {
    return {
image:"",
products:"",
selected:false,
     contact: [
   {
id: 'contact'}],

    }
  
  }, 

  methods:{


       nav(id) {

        const position = document.getElementById(id).offsetTop;
          // smooth scroll
         window.scrollTo({ top: position, behavior: "smooth" });  
    },

  }

}
</script>

<style lang="scss" scoped>

.container{

    padding: 2%;
    overflow-x: hidden;
        max-width: 2000px;
margin: auto;      

}

.hero-container {
 background:linear-gradient(rgba(0, 0, 0, 0.616),rgba(0, 0, 0, 0.616)),url('../assets/1.jpg');
 background-size: cover;
  box-sizing: border-box;
  background-position: right;
  min-height: 700px;

 color: white;
 padding: 0;
 margin: 0;
}



.text {
    padding: 5%;
    text-align: left;
    width: 50%;
                animation: moveright 1s linear;

border: 1px solid rgba(0, 0, 0, 0.425);;
border-radius: 0 35% 35% 0;
background: rgba(0, 0, 0, 0.425);


    h1{
            font-size: 60px;
            font-weight: 600;
            margin-bottom: 25px;
            text-transform: uppercase;
            letter-spacing: 2.5px;

            }

            
    .yellow-highliner{
            font-size: 60px;
            font-weight: 600;
            margin-bottom: 25px;
            text-transform: uppercase;
            letter-spacing: 2.5px;
            color:rgb(255, 208, 0);

            }

            h2{
              font-size: 35px;
            }

      p{
        font-size: 20px;
        padding: 15px 0;
        line-height: 30px;
      }
            button{
              font-size: 25px;
              border: 1px solid white;
              background: transparent;
              font-weight: bold;
              color: white;
              padding: 10px 25px;
              margin: 25px auto;
font-family: 'Lato', sans-serif;
              cursor:pointer;
                  transition: .5s ease-in-out;
                border-radius: 0 25px 25px 0;

              &:hover{
    background: black;
    color: rgb(238, 214, 0);
              transition: .4s ease-in-out;
              border: 1px solid black;
}
            }

    
}


  @keyframes moveleft {

        0% {
            transform: translateX(800px);
        }
        100% {
            transform: translateX(0px);
    
        }
    }
      @keyframes moveright {

        0% {
            transform: translateX(-800px);
        }
        100% {
            transform: translateX(0px);
    
        }
    }




@media (max-width:1000px) {

.hero-container{
      background: black;

}
  .container{
    flex-direction: column;
  }
  .background{ 
    display: none;
  }
  .text {
    margin: 2% 0 0 0;
    padding: 0;
    text-align: center;
    width: 100%;

    h1 {
    font-size: 50px;
  }

  span{
    font-size: 30px;
  }
  }

 
 
 .container-small{
    flex-direction: column;
 }
}

@media (max-width:700px) {
   .picture{
    flex-direction: column;
  }
   .container-small{
    flex-direction: row;
 }


}
@media (max-width:600px) {
   .picture{
    flex-direction: column;
  }
   .container-small{
    flex-direction: column;
 }
}

@media (max-width:400px) {

  .text {
    text-align: center;
    width: 100%;
                animation: moveright 1s linear;




    h1{
            font-size: 40px;
            font-weight: 600;
            margin-bottom: 25px;
            text-transform: uppercase;
            letter-spacing: 2.5px;

            }

            
    .yellow-highliner {
            font-size: 40px;
            font-weight: 600;
            margin-bottom: 25px;
            text-transform: uppercase;
            letter-spacing: 2.5px;
            color:rgb(255, 208, 0);

            }

            span{
              font-size: 25px;
            }

      p{
        font-size: 20px;
      }
            button{
              font-size: 20px;
              border: 1px solid white;
              border-radius: 25px;
              background: transparent;
              font-weight: bold;
              color: white;
              padding: 10px 25px;
              margin: 25px auto;
              cursor:pointer;
                  transition: .5s ease-in-out;


              &:hover{
       background:rgb(255, 208, 0);
    border: 1px solid transparent;
    cursor: pointer;
    transition: .5s ease-in-out;
    color:  black;
}
            }

    
}
   .big-picture{
  height: 400px;
  width: 250px;
  object-fit: cover;
  border-radius: 20px;
  padding: 10px;
}
}

</style>
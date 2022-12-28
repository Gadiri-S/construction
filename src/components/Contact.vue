<template>
  <div class="container"> 
   


    <div class="contact-container">
      <div class="container-img">
      </div>
      <div class="text">
<h1>Contact</h1>
<p>Prêts à travailler avec nous?</p>

<div> <router-link to="/contact"><button >Contact</button></router-link></div>
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
/*
    padding: 2%;
    overflow-x: hidden;
        max-width: 2000px;
margin: auto;      
*/
}

.contact-container {
display: grid;
grid-template-columns: repeat(4, 1fr);
grid-template-rows: 1fr;
grid-column-gap: 0px;
grid-row-gap: 0px;
}

.container-img { grid-area: 1 / 1 / 2 / 3;
 background:url('../assets/1.jpg');
 background-size: cover;
  box-sizing: border-box;
  background-position:top ;
}


.text { grid-area: 1 / 3 / 2 / 5;
  text-align: left;
background: #fdc23e;
padding: 20%;
         h1 {    padding: 20px 0;

  color: #000000;
  font-size: 32px;
  font-weight: 700;
  letter-spacing: 7px;
  text-align: center;
  text-transform: uppercase;
}

      p{
        font-size: 40px;
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
         }
}



@media (max-width:1200px) {

.contact-container{
  display: flex;
  flex-direction: column;

  .container-img{
    width: 100%;
    height: 400px;
  }

  .text{
    padding:10% ;
  }
}
}




</style>
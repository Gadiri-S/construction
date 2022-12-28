<template>
  <div class="container">
                    <h1>Nos services</h1>

    <div class="services">
        <router-link to='/demolition'>
<div class="demolition service">
    <div class="heading">
        <img src="../assets/hook.png" alt="" class="icon">
        <h2>Démolition</h2>
    </div>
    <div class="content">
    <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Atque eius tempore nesciunt assumenda sapiente cumque?</p>
<button>En savoir plus</button></div>
</div>
</router-link>

        <router-link to='/terrassement'>

<div class="terrassement service">
     <div class="heading">
        <img src="../assets/excavator.png" alt="" class="icon">
        <h2>Térrassement</h2>
    </div>
 <div class="content">
    <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Atque eius tempore nesciunt assumenda sapiente cumque?</p>
<button>En savoir plus</button></div></div>

        </router-link>

        <router-link to='/curage'>

<div class="curage service">
     <div class="heading">
        <img src="../assets/brickwall.png" alt="" class="icon">
        <h2>Curage</h2>
    </div>
 <div class="content">
    <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Atque eius tempore nesciunt assumenda sapiente cumque?</p>
<button>En savoir plus</button></div></div>

        </router-link>

        <router-link to='/remise-aux-normes'>

<div class="normes service">
     <div class="heading">
        <img src="../assets/multimeter.png" alt="" class="icon">
        <h2>Remise aux normes</h2>
    </div>
 <div class="content">
    <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Atque eius tempore nesciunt assumenda sapiente cumque?</p>
<button>En savoir plus</button></div></div>

        </router-link>

                <router-link to='/nettoyage-apres-incendie'>

<div class="incendie service">
     <div class="heading">
        <img src="../assets/fire.png" alt="" class="icon">
        <h2>Néttoyage après incendie</h2>
    </div>
 <div class="content">
    <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Atque eius tempore nesciunt assumenda sapiente cumque?</p>
<button>En savoir plus</button></div></div>

                </router-link>

        <router-link to='/raffraichissement'>

<div class="building service">
     <div class="heading">
        <img src="../assets/building.png" alt="" class="icon">
        <h2>Raffraîchissement</h2>
    </div>
 <div class="content">
    <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Atque eius tempore nesciunt assumenda sapiente cumque?</p>
<button>En savoir plus</button></div></div>

        </router-link>

    </div>
  </div>
</template>

<script>
export default {

}
</script>

<style lang="scss" scoped>
.container{
    padding: 2%;
    background-color: rgb(232, 238, 247);

}
.services {
display: grid;
grid-template-columns: repeat(3, 1fr);
grid-template-rows: repeat(2, 1fr);
grid-column-gap: 0px;
grid-row-gap: 0px;

}
.heading{
    display: flex;
    align-items: center;
}

h1 {    padding: 20px 0;

  color: #000000;
  font-size: 32px;
  font-weight: 700;
  letter-spacing: 7px;
  text-align: center;
  text-transform: uppercase;
}

h2{
    font-size: 25px;
}
.demolition { grid-area: 1 / 1 / 2 / 2; }
.terrassement { grid-area: 1 / 2 / 2 / 3; }
.curage { grid-area: 1 / 3 / 2 / 4; }
.normes { grid-area: 2 / 1 / 3 / 2; }
.incendie { grid-area: 2 / 2 / 3 / 3; }
.building { grid-area: 2 / 3 / 3 / 4; }

p{
    text-align: left;
    margin: 15px 0 ;
}
.icon{
    height: 60px;
    margin: 15px;
    position: relative;
    top: 0;
    transition: .4s ease-in-out;

}

.service:nth-child(even) {
    background-color: rgb(34, 34, 34);
}
.service{
    padding: 30px;
    background-color: rgb(24, 23, 23);
    color: white;
        transition: .4s ease-in-out;
        border: 1px solid  transparent;

    &:hover{
        border: 1px solid  #fdc23e;
cursor: pointer;
        transition: .4s ease-in-out;


        .icon{
transition: .4s ease-in-out;
    top: 15px;
    }}
}

.content{
    display: flex;
    flex-direction: column;
}
button{
    padding: 5px;
    font-size: 20px;
    width: 140px;
    cursor: pointer;

}

@media (max-width:1200px) {
    .services{
        display: flex;
        flex-wrap: wrap;
        justify-content: center;
       

        .service{
            width: 300px;
        }
    }
}
</style>
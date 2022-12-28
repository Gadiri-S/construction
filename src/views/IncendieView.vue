<template>
  <div class="container">
<Header/>
    <div class="about-container">

        <div>
        <img src="../assets/f.webp" class="img" alt=""></div>

        <div class="text">
            <h1>néttoyage après incendie</h1>
 <p>Lorem ipsum dolor sit, amet consectetur adipisicing elit. Eum suscipit, esse magnam in deleniti, sed distinctio facilis, cumque vero tempore nostrum doloremque possimus. Sint nam natus sequi culpa commodi numquam aliquid! Quo, delectus! Laboriosam, ratione esse? Tempora optio illo ad, itaque, tempore assumenda eum necessitatibus eaque doloribus eligendi, dignissimos culpa!</p>
                    <p>Lorem ipsum dolor sit, amet consectetur adipisicing elit. Eum suscipit, esse magnam in deleniti, sed distinctio facilis, cumque vero tempore nostrum doloremque possimus. Sint nam natus sequi culpa commodi numquam aliquid! Quo, delectus! Laboriosam, ratione esse? Tempora optio illo ad, itaque, tempore assumenda eum necessitatibus eaque doloribus eligendi, dignissimos culpa!</p>

                    <p>Lorem ipsum dolor sit, amet consectetur adipisicing elit. Eum suscipit, esse magnam in deleniti, sed distinctio facilis, cumque vero tempore nostrum doloremque possimus. Sint nam natus sequi culpa commodi numquam aliquid! Quo, delectus! Laboriosam, ratione esse? Tempora optio illo ad, itaque, tempore assumenda eum necessitatibus eaque doloribus eligendi, dignissimos culpa!</p>

        </div>
    </div>
    <div class="advantages">
      <div class="advantage">
       <div> <img src="../assets/clock.png" alt="" class="icon"></div>
        <span>Respect des délais</span>
      </div>
          <div class="advantage">
       <div> <img src="../assets/high-quality.png" alt="" class="icon"></div>
                <span>Proffesionnalisme</span>

      </div>
          <div class="advantage">
       <div> <img src="../assets/transparency.png" alt="" class="icon"></div>
                <span>Transparence</span>

      </div>
          <div class="advantage">
       <div> <img src="../assets/engineering.png" alt="" class="icon"></div>
                <span>Expertise</span>

      </div>
    </div>
    <Contact/>
    <Footer/>
  </div>
</template>

<script>

import Contact from '@/components/Contact.vue'
import Footer from '@/components/Footer.vue'
import Header from '@/components/Header-content.vue'
export default {
components: {
Contact,Footer,Header
  },
    mounted(){
      window.scrollTo(0,0)
    },
}
</script>

<style scoped lang='scss'>
.container{
}

.about-container{
      padding: 2%;

    display: flex;
    justify-content: space-between;

    .text{
            padding: 2%;
            text-align: left;
         h1 {    

  color: #000000;
  font-size: 32px;
  font-weight: 700;
  letter-spacing: 7px;
  text-transform: uppercase;
}

p{
    font-size: 18px;
    line-height: 20px;
    margin: 15px 0;
}
  width: 50vw;


    }
}

.img{
height: 100%;
  width: 30vw;
  object-fit: cover;
  border-radius: 35% 0 0 35%;
  }

.advantages{
      padding: 2%;

  display: flex;
  margin: 25px 0;
}
  .advantage{
    display: flex;
    flex-direction: column;
    align-items: center;
    background: #fdc23e;
    width: 25%;
    padding: 15px 0;

    span{
      font-size: 25px;
    }
  }

  .icon{
    height: 60px;
    margin: 15px;
    position: relative;
    top: 0;
    transition: .4s ease-in-out;

}
</style>
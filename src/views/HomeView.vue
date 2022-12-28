<template>
  <div class="home">
    
    <Hero v-once />
    <About id='about' v-once />
        <Services id='services' v-once />

    <Contact v-once />
     <Footer v-once />


  </div>
</template>

<script>
// @ is an alias to /src
import Hero from '@/components/Hero.vue'
import About from '@/components/About.vue'
import Contact from '@/components/Contact.vue'
import Services from '@/components/Services.vue'
import Footer from '@/components/Footer.vue'







export default {
  name: 'HomeView',
  components: {
    Hero,Contact,Services,Footer,About
  }
}

</script>

<style scoped>
.home{

}
</style>
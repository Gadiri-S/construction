<template>

  <router-view/>
</template>

<style lang="scss">

@import url('https://fonts.googleapis.com/css2?family=Poppins:ital,wght@0,100;0,200;0,300;0,400;0,500;0,600;0,700;0,800;0,900;1,100;1,200;1,300;1,400;1,500;1,600;1,700;1,800;1,900&family=Raleway:wght@400;500;600;700;800;900&display=swap');
#app {
font-family: 'Lato', sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;


}

h1{
font-family: 'Alexandria', sans-serif;

}

*{
  padding: 0;
  margin: 0;

}


  a{

    text-decoration: none;
          color: inherit;


    &:visited{
      color: inherit;
    }
    &.router-link-exact-active {
      color: inherit;
    }
  }


 
</style>

<template lang="pug">
div
   nav
      img( src="~/public/Nyllde.png" )

      .nav-items
         NuxtLink( to="/" )
            | Home

         NuxtLink( to="/shows" )
            | Shows
            
         NuxtLink( to="/about" )
            | About

   .content
      slot
</template>

<style lang="scss">

@mixin so($or) {
  @media (orientation: $or) {
    @content
  }
};

@import url('https://fonts.googleapis.com/css2?family=Syne:wght@700;800&display=swap');

* {
   margin: 0;
   box-sizing: border-box;
   font-family: 'Syne', sans-serif;
}
nav {
   background: rgba(0, 0, 0, 0.6);
   backdrop-filter: blur(5px);
   z-index: 999;
   color: white;
   position: fixed;
   width: 95%;
   padding: .7em 4em;
   margin: 1.5% 2%;
   height: 3.5em;
   // border-radius: 0 0 10px 10px;
   border-radius: 10px;
   display: flex;
   justify-content: space-between;

   top: -5em;
   opacity: 0;
   animation: slideOpacity 1s 1s forwards;

   img {
      width: 35px;
      border-radius: 6px
   }

   @include so(portrait) {
      justify-content: center;

      img {
         display: none
      }
   }

   & > * {
      font-weight: 800;
   }

   .nav-items {
      display: flex;
      gap: 3em;
      align-items: center;
      justify-content: center;

      & > * {
      font-weight: 700;
      text-decoration: none;
      color: white;
      }
   }
}

.content {
   // margin-top: 5em;
   box-shadow: 0 -5em 10px 10px #000;
}


@keyframes slideOpacity {
  to {
    transform: translateX(0) rotate(0deg);
    opacity: 1;
    top: 0;
  }
}

</style>
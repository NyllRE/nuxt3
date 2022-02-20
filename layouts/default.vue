<template lang="pug">
div
   nav
      img( src="~/public/Nyllde.png" )

      .nav-items
         NuxtLink( to="/" )
            | Home

         NuxtLink( to="/shows" )
            | Shows
            
         NuxtLink( to="/about/me" )
            | About

   .content
      slot
</template>

<style lang="scss">
@import url('https://fonts.googleapis.com/css2?family=Syne:wght@700;800&display=swap');

* {
   margin: 0;
   box-sizing: border-box;
   font-family: 'Syne', sans-serif;
}
nav {
   background: rgba(0, 0, 0, 0.631);
   backdrop-filter: blur(5px);
   color: white;
   position: fixed;
   top: 0;
   width: 98%;
   padding: .7em 4em;
   margin: 1em;
   // border-radius: 0 0 10px 10px;
   border-radius: 10px;
   display: flex;
   justify-content: space-between;
   img {
      width: 35px;
      border-radius: 6px
   }
}
nav > * {
   font-weight: 800;
}
.nav-items {
   display: flex;
   gap: 30px;
   align-items: center;
   justify-content: center;

   & > * {
   font-weight: 700;
   text-decoration: none;
   color: white;
   }
}

.content {
   margin-top: 5em;
}

</style>
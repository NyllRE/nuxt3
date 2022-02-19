<template>
   <div>
      <header>
         <img src="~/public/Nyllde.png"/>
         <nav>
            <NuxtLink to="/">
            Home
            </NuxtLink>
            <NuxtLink to="/">
            Other Link
            </NuxtLink>
            <NuxtLink to="/about/me">
            About
            </NuxtLink>
         </nav>
      </header>
      <div class="content">
         <slot></slot>
      </div>
   </div>
</template>

<style lang="scss">
@import url('https://fonts.googleapis.com/css2?family=Syne:wght@700;800&display=swap');

* {
   margin: 0;
   box-sizing: border-box;
   font-family: 'Syne', sans-serif;
}
header {
   background: rgba(0, 0, 0, 0.631);
   backdrop-filter: blur(5px);
   color: white;
   position: fixed;
   top: 0;
   width: 100%;
   padding: .7em 4em;
   border-radius: 0 0 10px 10px;
   display: flex;
   justify-content: space-between;
   img {
      width: 35px;
      border-radius: 6px
   }
}
header > * {
   font-weight: 800;
}
nav {
   display: flex;
   gap: 30px;
   align-items: center;
   justify-content: center;
}

nav > * {
   font-weight: 700;
   text-decoration: none;
   color: white;
}

.content {
   margin-top: 5em;
}

</style>
<template>
   <div>
      <header>
         <h2>Title</h2>
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
      <slot></slot>
   </div>
</template>

<style>
* {
   margin: 0;
   box-sizing: border-box;
   font-family: Verdana, Geneva, Tahoma, sans-serif;
}
header {
   background: rgba(0, 0, 0, 0.631);
   color: white;
   padding: .7em 4em;
   border-radius: 0 0 10px 10px;
   display: flex;
   justify-content: space-between;
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

</style>
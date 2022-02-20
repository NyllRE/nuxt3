<script setup lang="ts">
import {ref} from 'vue';

useMeta({
      title: 'Home Page'
    })

</script>


<template lang="pug">

.container
  .header-container
    .wrapper
      header
        .hero-content
          h1 Hi, I'm Nyll 
          p I design beautiful Full Stack Web Applications
          a( href="/about" ) Contact Me 

        .hero-image
          img( src="~/public/Nyllde.png" )

      //- .social-icons
      //-   img

</template>


<style scoped lang="scss">

@mixin screen-min($min) {
  @media (min-width: $min) {
    @content
  }
};

@mixin screen-orientation($or) {
  @media (orientation: $or) {
    @content
  }
};

.container {
  display: flex;
  align-items: center;
  justify-content: center;
  overflow-x: hidden;
  width: 100%;
  height: 100vh;
  color:white;

  background: url('~/public/citybg.jpg') #0006;
  background-size: cover;
  background-position: center;
  background-repeat: no-repeat;
  background-blend-mode: color;

  .header-container {
    .wrapper {
      width: 75em;
      margin: 0 auto;
      @include screen-min(1440px) {max-width: 70em;}
      @include screen-min(1080px) {max-width: 65em;}

      header {
        display: flex;
        align-items: center;
        justify-content: space-between;
        
        @include screen-orientation(portrait) {
          flex-direction: column;
          font-size: .5em;
          text-align: center;
        }

        .hero-content {
          

          @include screen-orientation(portrait) {
            margin-bottom: 5em;
            text-align: center;
            justify-content: center;
          }
          h1 {
            font-style: normal;
            font-weight: 800;
            font-size: 4em;
            line-height: 2em;
            transform: translateX(-5em);
            animation: slideOpacity .8s forwards;

            @include screen-orientation(portrait) {
              font-size: 5em;
            }
          }

          p {
            font-size: 1.8em;
            line-height: 1.5em;
            color: #91d4d8;
            margin-bottom: .8em;
            transform: translateX(-5em);
            opacity: 0;
            animation: slideOpacity .7s .3s forwards;
            width: 100%;

            @include screen-orientation(portrait) {
              font-size: 2.5em;
              margin: 0 auto;
              overflow: wrap;
              inline-size: 80%;
              text-align: center;
              margin-bottom: 1em;
            }
          }

          a {
            text-decoration: none;
            font-size: 1em;
            color: white;
            padding: .8em 2.5em;
            background: linear-gradient(rgb(228, 0, 228), rgb(255, 29, 29));
            color: white;
            border-radius: 10px;
            transition: .3s;
            display: inline-block;
            transform: translateX(-5em);
            opacity: 0;
            animation: slideOpacity .6s .6s forwards;

            &:hover {
              transform: scale(1.1);
            }

            @include screen-orientation(portrait) {
              font-size: 1.5em;
            }
          }
        }
        .hero-image {
          position: relative;
          box-shadow: 0 0 40px #000d;
          transform: translateX(5em) rotate(10deg);
          opacity: 0;
          animation: slideOpacity .5s .9s forwards;

          img {
            width: 30em;
            border-radius: 3em;
            transform: rotate(-4deg);
            transition: .3s;

            &:hover {
              transform: rotate(0deg);
            }

            @include screen-min(1440px) {width: 25em;}
            @include screen-min(1080px) {max-width: 22em;}
            @include screen-orientation(portrait) {
              display: none;
            }
          }
        }
      }
    }
  }
}

@keyframes slideOpacity {
  to {
    transform: translateX(0) rotate(0deg);
    opacity: 1;
  }
}


</style>
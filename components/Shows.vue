<script setup lang="ts">
import {ref} from "vue"

const searchText = ref("")
const myData = ref([]) as any;

async function searchForShows() {
  const data = await fetch(`/api/shows?search=${searchText.value}`)
  const json = await data.json()
  console.log('json', json)
  myData.value = json
}
</script>

<template lang="pug">
.container
  h1 Search For Shows
  form.form(@submit.prevent='searchForShows')
    input(type='text' v-model='searchText')
    button Search 
  .shows
    .show(v-for='show in myData' :key='show.id')
      img(:src='show.show?.image?.medium' alt='missing image')
</template>

<style scoped lang="scss">
.container {

  width: 100%;
  height: 100vh;

  background: url('~/public/streetgirl.jpg');
  background-size: cover;
  background-position: center;
  background-repeat: no-repeat;

  display: flex;
  justify-content: center;
  align-items: center;
  flex-direction: column;

  h1 {
    font-size: 50px;
    font-weight: 700;
    margin-bottom: 20px;
    color: #fff;
  }
  
}
.shows {
  display: grid;
  margin-top: 30px;
  grid-template-columns: 250px 250px 250px;
  row-gap: 30px;
  padding: 3em;
  background: #0005;
  height: 60%;
  overflow: hidden scroll;
  border-radius: 30px;
  backdrop-filter: blur(9px);
  border: 1px solid #fff3;
  box-shadow: 0 0 20px #000a;
  &::-webkit-scrollbar { width: 0px }
  img {
    border-radius: 10px
  }
}
// .shows::
.form {
  display: flex;
  flex-direction: column;
  align-items: center;
  input {
    border: none;
    padding: .4em;
    border-radius: 10px;
    width: 20em;
    background: linear-gradient(145deg, #c7c7c7, #ececec);
    box-shadow:  10px 10px 24px #b1b1b133,
              -10px -10px 24px #ffffff33;
  }
  button {
    border: none;
    width: 60%;
    background: linear-gradient(145deg, #c7c7c7, #ececec);
    box-shadow:  10px 10px 24px #b1b1b133,
              -10px -10px 24px #ffffff33;
    color: rgb(70, 70, 70);
    font-weight: 600;
    padding: .6em 2em;
    margin: 1em;
    border-radius: 7px;
  }
}
</style>
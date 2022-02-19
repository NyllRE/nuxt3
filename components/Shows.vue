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

<template>
<div class="container">
  <h1>Search For Shows</h1>
  <form class="form" @submit.prevent="searchForShows">
    <input type="text" v-model="searchText">
    <button> Search </button>
  </form>


  <div class="shows">
    <div class="show" v-for="show in myData" :key="show.id">
      <img :src="show.show?.image?.medium" alt="missing image" />
    </div>
  </div>
</div>

</template>

<style scoped lang="scss">
.container {
  margin-top: 20px;
  width: 100%;
  display: flex;
  justify-content: center;
  align-items: center;
  flex-direction: column;
  h1 {
    font-size: 50px;
    font-weight: 700;
    margin-bottom: 20px;
  }
}
.shows {
  display: grid;
  margin-top: 30px;
  grid-template-columns: 250px 250px 250px;
  row-gap: 30px;
  img {
    border-radius: 10px
  }
}
.form {
  display: flex;
  flex-direction: column;
  align-items: center;
  input {
    border: none;
    padding: .4em;
    border-radius: 10px;
    background: linear-gradient(145deg, #c7c7c7, #ececec);
    box-shadow:  17px 17px 24px #b1b1b1,
              -17px -17px 24px #ffffff;
  }
  button {
    border: none;
    width: 60%;
    background: linear-gradient(145deg, #c7c7c7, #ececec);
    box-shadow:  10px 10px 24px #b1b1b1,
              -10px -10px 24px #ffffff;
    color: rgb(70, 70, 70);
    font-weight: 600;
    padding: .6em 2em;
    margin: 1em;
    border-radius: 7px;
  }
}
</style>
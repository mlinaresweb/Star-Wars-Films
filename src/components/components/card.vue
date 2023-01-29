<template>
    <div class="container-cards">
        <template v-if="films.length > 0 ">
        <div class="card" v-for="(film, index) in films" :key="film.title">
            
            <h2>{{film.title}}</h2> 
            <img class="card-img" :src="'https://starwars-visualguide.com/assets/img/films/'+(index+1)+'.jpg'"  >
            <p>{{film.opening_crawl}}</p>
            <button  @click="() => popupTriggers = index">More Information</button>
        <popup 
        v-if="index == popupTriggers" 
        :TogglePopup="() => TogglePopup()">
        <div class="container-popup">  
            <p><b> Director: </b>{{film.director}}</p>
            <p><b>Release Year:</b> {{film.release_date.split("-")[0]}}</p>
            <h2>In this film there are:</h2>
            <p>{{film.characters.length}}<b> characters</b></p>
            <p>{{film.starships.length}}<b> starships</b></p>
            <p>{{film.vehicles.length}}<b> vehicles</b></p>
            <p>{{film.species.length}}<b> species</b></p>
        </div>
            </popup>
        </div>
    </template>
    <template v-else>
        <slot></slot>
    </template>
</div>
</template>


<script setup>
import popup from './popup.vue';
import { onMounted, ref,} from 'vue';

//Get information of API and save in films.value
const films = ref([]);
onMounted(async () =>{
    const response = await fetch("https://swapi.dev/api/films/");
    const resultado = await response.json()
    films.value = resultado.results
})

//start var in -1 for count index and do the action of change information of popup
const popupTriggers = ref(-1)

const TogglePopup = () =>{
    popupTriggers.value = -1
}

</script>

<style scoped>

.card{
    width: 350px;
    margin: 20px;
    background-color: rgba(155, 145, 145, 0.3);
    padding: 10px;
    border-radius: 15px;
}

.card > p{
    margin: 7px;
}

.card > p > b{
    font-size: 25px;
}

.card-img{
width: 98%;
}

@media only screen and (min-width: 1600px){
   
   .card{
    width: 500px;
}
}

</style>




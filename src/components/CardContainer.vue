<template>
    <div class="my_container">
        <div class="genre">
            <SelectGenre @SelectGenre="compareGenre"/>
        </div>
        <CardComponent v-for="card, index in filterGenre" :key="index" :SingleCard="card"/>
    </div>
</template>

<script>
import CardComponent from './CardComponent.vue'
import SelectGenre from './SelectGenre.vue'
import axios from "axios"

export default {
    name: 'CardContainer',
    components: {
        CardComponent,
        SelectGenre
    },
    data(){
        return{
            urlApi: 'https://flynn.boolean.careers/exercises/api/array/music',
            arrayCards: [],
            genre: ''
        }
    },
    created(){
        this.createCard()
    },
    computed:{
        filterGenre(){
            if(this.genre == 'All'){
                return this.arrayCards;
            }

            return this.arrayCards.filter((card) => {
                return card.genre.includes(this.genre)
            })
        }
    },
    methods: {
        createCard(){
            axios.get(this.urlApi).then((element) => {
                this.arrayCards = element.data.response
            })
        },
        compareGenre(genere){
            this.genre = genere
        }
    }
}
</script>

<style lang="scss" scoped>
.my_container{
    width: 70%;
    margin: 0 auto;
    display: flex;
    flex-wrap: wrap;
    position: relative;

    .genre{
        position: absolute;
        top: -50px;
        color: white;
    }
}

</style>
<template>
    <div class="my_container">
        <CardComponent v-for="card, index in arrayCards" :key="index" :SingleCard="card"/>
    </div>
</template>

<script>
import CardComponent from './CardComponent.vue'
import axios from "axios"

export default {
    name: 'CardContainer',
    components: {
        CardComponent
    },
    data(){
        return{
            urlApi: 'https://flynn.boolean.careers/exercises/api/array/music',
            arrayCards: []
        }
    },
    created(){
        this.createCard()
    },
    methods: {
        createCard(){
            axios.get(this.urlApi).then((element) => {
                this.arrayCards = element.data.response
                console.log(this.arrayCards)
            })
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
    justify-content: space-between;
}

</style>
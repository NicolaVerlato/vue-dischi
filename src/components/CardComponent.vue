<template>
    <div class="single_card">
        <img :src="SingleCard.poster" :alt="SingleCard.author">
        <h3>
            {{ SingleCard.title }}
        </h3>
        <div class="artist">
            <div class="name">
                {{ SingleCard.author }}
            </div>
            <div class="year">
                {{ SingleCard.year }}
            </div>
        </div>
    </div>
</template>

<script>
export default {
    name: 'CardComponent',
    props: {
        SingleCard: Object
    }
}
</script>

<style lang="scss" scoped>
@import '../style/variables';

.single_card{
    padding: 20px;
    background-color: $card_bg_color;
    width: calc(20% - 20px);
    text-align: center;
    margin-bottom: 20px;

    h3{
        color: $white;
        padding: 20px;
        text-transform: uppercase;
    }
    .artist{
        color: grey;
    }
    
}
</style>
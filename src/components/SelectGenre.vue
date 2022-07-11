<template>
    <div class="select-genre">
        <label for="genre">Seleziona il genere</label>

        <select v-model="selected" @change="$emit('SelectGenre', selected)">
            <option>Jazz</option>
            <option>Metal</option>
            <option>Pop</option>
            <option>Rock</option>
            
        </select>
         <span>{{selected}}</span>
    </div>
</template>

<script>
export default {
    name: 'SelectGenre',
    props:{
        option: Object
    },
    data(){
        return{
            selected: null
        }
    },
    computed:{
        filteredGenre(genre){
            return this.$emit(genre)
        }
    },
    
}
</script>

<style lang="scss" scoped>
select{
    margin-left: 5px;
}
</style>
<template>
    <div class="my_header">
        <img src="../assets/img/logo-small.svg" alt="Logo">
    </div>
</template>

<script>
export default {
    name: 'HeaderComponent',
}
</script>

<style lang="scss" scoped>
@import '../style/variables';
.my_header{
    background-color: $card_bg_color;
    height: 80px;
    margin-bottom: 80px;
    
    img{
        width: 50px;
        padding-top: 15px;
        margin-left: 30px;
    }
}
</style>
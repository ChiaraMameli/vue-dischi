<template>
<header>
    <img :src="logo" alt="">
    <SelectForm :options="genresList" @change-option="changeGenre"/>
</header>
</template>

<script>
import SelectForm from './SelectForm.vue'
export default {
    name: "BaseHeader",
    data() {
        return {
            logo: require("../assets/img/logo.svg"),
        };
    },
    components: { 
        SelectForm 
        },
    props:{
        genresList: Array,
    },
    methods:{
        changeGenre(genre){
            this.$emit('change-option', genre)
        }
    }
}
</script>

<style lang="scss" scoped>
@import '../assets/sass/_vars.scss';
header {
    height: 60px;
    background-color: $light_blue;
    padding: 10px;

    display: flex;
    justify-content: space-between;
    
    img{
        max-height: 100%;
        filter: invert(71%) sepia(54%) saturate(475%) hue-rotate(67deg) brightness(94%) contrast(91%);
        margin-left: 10px;
        }
}
</style>
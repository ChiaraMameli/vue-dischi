<template>
<header>
    <img :src="logo" alt="">
</header>
</template>

<script>
export default {
    name: 'BaseHeader',
    data(){
        return{
            logo: require('../assets/img/logo.svg')
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
    img{
        max-height: 100%;
        filter: invert(71%) sepia(54%) saturate(475%) hue-rotate(67deg) brightness(94%) contrast(91%);
        margin-left: 10px;
        }
}
</style>
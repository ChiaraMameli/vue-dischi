<template>
<main>
    <div class="container">
        <div class="box">
            <DiscCard />
        </div>
    </div>
</main>
</template>

<script>
import DiscCard from './DiscCard.vue';
import axios from 'axios';

export default {
    name: "ContentSection",
    components: { 
        DiscCard,
        },
    mounted(){
        axios.get('https://flynn.boolean.careers/exercises/api/array/music').then((res) => {
            console.log(res.data)
        })
    }
}
</script>

<style lang="scss" scoped>
@import '../assets/sass/vars';
    main{
        background-color: $dark_blue;
        height: 100vh;

        .box{
            display: flex;
            flex-wrap: wrap;
            justify-content: space-between;

            padding: 50px 0;
        }
    }
</style>